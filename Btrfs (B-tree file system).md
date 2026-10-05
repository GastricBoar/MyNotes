---
date: 2026-01-20
tags:
  - linux
  - informatica
  - pubblico

---
# Btrfs (B-tree file system)
---
Un [[Filesystem]] moderno, pensato tenendo in mente snapshot, rollback, compressione e gestione avanzata dello spazio.

### I filesystem tradizionali come funzionano?
Prendi dei filesystem più tradizionali come [[ext4 (fourth extended filesystem)]] o [[NTFS (New Technology File System)]], quelli funzionano così:

```
DISCO
└── PARTIZIONE
    └── FILESYSTEM
        └── FILE

```

Ogni partizione:

- contiene un unico grosso filesystem (es. un intero filesystem ext4 o un intero filesystem NTFS).
- montato per intero su una directory (come `/` o `/home`).
- dentro ogni filesystem ci sono file e cartelle.

Se monti ext4 su `/`, monti l'intero filesystem su quella directory lì.

### Invece Btrfs? cosa sono i subvolumi?
Btrfs invece usa i subvolumi: root logiche indipendenti all'interno dello stesso filesystem Btrfs.

All'interno di un singolo filesystem possono esistere più subvolumi in questo modo:

```
DISCO / PARTIZIONE
└── FILESYSTEM BTRFS
    ├── subvolume @
    ├── subvolume @home # il contenuto della home
    ├── subvolume @log  # una delle cartelle di log
    └── subvolume @pkg  # la cartella con la cache di pacman

```

Ogni subvolume:

- **ha una propria root**
- **può essere montato separatamente**
- **può avere tanti snapshot indipendenti dagli altri subvolumi**
- **convivide lo spazio su disco con gli altri subvolumi**
- **fa parte dello stesso filesystem**
- **NON è una partizione:** una partizione è separata fisicamente dal resto delle altre partizioni, mentre un subvolume è un'astrazione logica.

### Perchè i subvolumi sono vantaggiosi?
Sono vantaggiosi perchè se usi uno strumento per snapshot tipo [[Snapper]] puoi fare cose tipo:
- fare snapshot solo di `/`
- escludere `/home`
- escludere `/var/log`
- rollback del sistema **senza perdere i dati**

Per esempio, potresti voler mettere tutto il contenuto della cartella log in un subvolume e poi ignorarlo in fase di snapshot, perchè quella pesa e non ha senso di esistere in uno snapshot.

### Montare un subvolume
Per utilizzare un subvolume devi prima montarlo su una directory, per esempio:

```
@ → montato su /
@home → montato su /home
@log → montato su /var/log
@pkg → montato su /var/cache/pacman/pkg
```

Quando monti un subvolume su una directory "copri" il contenuto di quella directory.

Per fare un esempio pratico:

- monti il subvolume `@` su `/`
- dopo il mount, quando accedi a `/` non stai davvero accedendo a `/` della directory di prima
- stai accedendo alla root del subvolume `@`, resa visibile su `/`
- la root precedente è stata nascosta sotto il mount del subvolume
- la root precedente è ancora lì fisicamente ma non è più visibile finchè il mount è attivo

---
- [[Mount points in Linux]]