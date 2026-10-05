---
date: 2026-01-14
tags:
  - informatica
  - linux
  - pubblico

---
# Mount points in Linux
---
Un punto di montaggio, ti indica in quale cartella è stato agganciato il filesystem di un disco storage (per esempio /mnt/backup). Quando monti un disco dici al sistema "in questa cartella devi mettere il contenuto di questo disco"

Per [[Linux]] un disco ha tre strati concettuali:

1. Collegato fisicamente (USB, SATA, ecc.)
2. Riconosciuto dal [[Kernel]].
3. Montato nel filesystem.

Qui si torna al concetto di [[Everything is a file]].

In Linux esiste un unico grosso [[Filesystem]], che parte da /.  A partire da lì, viene tutto innestato a cascata come fosse un unico grande albero:

```
/
├── home
├── mnt
│   ├── backup # un disco di backup
│   └── media  # un disco per i film
├── etc
└── var

```

###  E Windows invece?
Windows non funziona così, in Windows ogni disco/partizione ha una sua lettera di unità è una radice propria in questo modo:

```
C:\Users\Mario
D:\Film
E:\Backup

```

---
[[lsblk (list block devices)]]
[[Struttura delle directory Linux]]