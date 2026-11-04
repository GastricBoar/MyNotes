---
date: 2026-11-05-20-18
tags:
  - informatica
  - linux
  - pubblico
---
# Struttura del filesystem Linux
---
Il filesystem che organizza file e directory in Linux. 

### Come funziona?
A differenza di Windows, che alle partizioni assegna lettere di unità come `C:` e `D:`, Linux adotta una struttura gerarchica ad albero, dove tutte le risorse del filesystem si diramano a partire da un'unica directory, chiamata `/` (root).

Dischi, partizioni, dispositivi e filesystem differenti possono essere collegati a questa radice attraverso un meccanismo: il mount.

Ecco un filesystem Linux:

```
/
├── bin
├── boot
├── dev
├── etc
├── home
│   ├── paolo
│   └── mario
├── lib
├── media
├── mnt
├── opt
├── proc
├── root
├── run
├── sbin
├── srv
├── sys
├── tmp
├── usr
└── var
```

Guarda quante directory montate sopra la radice, son tante eh?

#### Il Filesystem Hierarchy Standard (FHS)
Vedi quelle directory sopra? ognuna di quelle directory sta esattamente dove dovrebbe stare, e la storia è questa:

- Negli anni '80/'90 esistevano diverse varianti di Unix, ognuna con le proprie convenzioni per organizzare file e directory.
  
- Era un problema per sviluppatori e amministratori di sistema, che per ritrovare i loro file dovevano tenere a mente tutte queste convenzioni differenti. Ma allora come si fa?

- Nel 1994 Daniel Quinlan pubblicò il Filesystem Standard (FSSTND), un primo tentativo di standardizzare l'organizzazione del filesystem Linux.

- Il progetto si evolse nel Filesystem Hierarchy Standard (FHS), con l'obiettivo di definire una convenzione condivisa per l'organizzazione di file e directory. 

- A standard adottato, se un programma deve leggere un file di configurazione, può aspettarsi di trovarlo in `/etc`, mentre i log di sistema li trova in `/var/log`.

Ecco le directory definite dallo standard, in una gloriosa tabella:

#### `/` (Root directory)
La directory radice, dalla quale parte tutta la struttura gerarchica; ogni percorso assoluto in Linux inizia da `/`.

#### `/bin` (User binaries)
Contiene i comandi essenziali utilizzabili da tutti gli utenti; per esempio, può contenere `ls`, `cp`, `mv`, `cat` e `bash`.

Nelle distribuzioni moderne, `/bin` è spesso un collegamento simbolico a `/usr/bin`. Leggiti la storia.

#### `/sbin` (System binaries)
Contiene i comandi essenziali per amministrazione, manutenzione e configurazione del sistema; per esempio, ne fanno parte strumenti come `fsck`, `reboot` e `ip`, a seconda della distribuzione.

Nelle distribuzioni moderne, `/sbin` è spesso un collegamento simbolico a `/usr/sbin`.

#### `/boot` 
Contiene file necessari per avviare Linux, per esempio:

- `vmlinuz`: immagine del kernel Linux.
- `initramfs`: filesystem utilizzato in avvio per caricare driver e preparare il sistema.
- Directory e file di configurazione del bootloader, come GRUB.

Se file di questa directory vengono danneggiati, il sistema potrebbe non riuscire ad avviarsi.

#### `/dev` (Device files)
Contiene file particolari che rappresentano dispositivi hardware o virtuali. "Everything is a file" è uno dei principi Unix, e di fatti, anche i dispositivi possono esser esposti tramite questi file speciali. 

Ad esempio:

- `/dev/sda`: un dispositivo di archiviazione (HDD, SSD SATA, chiavette USB etc.)
- `/dev/nvme0n1`: un dispositivo NVMe.
- `/dev/null`: un dispositivo virtuale che scarta qualsiasi dato ricevuto.
- `/dev/tty`: un dispositivo virtuale che rappresenta il terminale di controllo del processo corrente, approfonisci se vuoi.

Questa organizzazione su file permette ai programmi di interagire con dispositivi attraverso comuni operazioni di input/output del sistema.

#### `/etc` (Configuration files)
Contiene file di configurazione del sistema operativo e dei servizi installati.

Ad esempio:

- `/etc/passwd`: informazioni sugli account locali.
- `/etc/shadow`: informazioni sulle password e sulla loro scadenza.
- `/etc/fstab`: configurazione dei filesystem da montare.
- `/etc/hosts`: associazioni locali tra hostname e indirizzi IP.
- `/etc/ssh/sshd_config`: configurazione del server SSH.

È una delle directory più importanti per gli amministratori, perché gran parte della configurazione del sistema e dei servizi viene gestita attraverso i file contenuti al suo interno. Leggi [[etc (Et Cetera)]].

#### `/home` (User home directories)
Contiene le directory personali degli utenti del sistema, dove conservano file personali e configurazioni.

Per fare un'esempio è `/home/paolo`, ma ci sono anche dei file nascosti come `.bashrc`, `.profile` e la directory `.ssh`, usati per configurare l'ambiente personale dell'utente.

#### `/root` (Root home directory)
La directory personale dell'utente `root`, l'amministratore con privilegi massimi sul sistema; quando accede al sistema, la sua directory personale è quindi `/root`, non `/home/root`.

È separata da `/home` perché serve sia disponibile anche in situazioni in cui le altre directory, ad esempio quelle contenute in filesystem separati, non sono ancora montate.

#### `/lib` (Essential shared libraries)
Contiene le librerie condivise necessarie ai programmi fondamentali del sistema, oltre ai moduli del kernel. 

Sono librerie importanti perché permettono ai programmi di utilizzare codice condiviso senza doverlo includere per intero al loro interno; ad esempio, può contenere librerie utilizzate dai comandi `bash` e `ls`.

Nelle distribuzioni moderne, `/lib` è spesso un collegamento simbolico a `/usr/lib`.

#### `/media` (Removable media mount points)
È una directory utilizzata come punto di mount per supporti rimovibili.

Ad esempio: quando colleghi una chiavetta USB, il sistema potrebbe montarla automaticamente in un percorso come `/media/paolo/USB`.

### `/mnt` (Temporary mount point)
È una directory utilizzata dagli amministratori come punto di mount temporaneo per filesystem e dispositivi di archiviazione. A PC riavviato il dispositivo non sarà più montato in questa directory.

Puoi montare manualmente una partizione in `/mnt` così: `sudo mount /dev/sdb1 /mnt`

È utile durante attività di manutenzione varie. A differenza di `/media`, non è specificamente dedicata ai supporti rimovibili.

### `/opt` (Optional application software)
Contiene software aggiuntivo installato al di fuori della normale organizzazione dei pacchetti di sistema. Facendo un'esempio:

- Se installi Firefox tramite packet manager, l'eseguibile va in `/usr/bin`, le librerie in `/usr/lib`, i file di configurazione in `/etc` e così via.
- Se invece Google distribuisce Chrome come applicazione autonoma con tutti i file raccolti dentro una sua directory, allora va a finire dentro `/opt/google/chrome`.

Le applicazioni di terze parti sono spesso installate in `/opt/google/chrome`.

#### `/proc` (Process and kernel information)
È un filesystem virtuale che espone informazioni su processi e kernel. Quando dico "filesystem virtuale" intendo questo:

- Normalmente, quando apri un file, leggi informazioni che qualcuno ha già salvato a disco.
  
- `/proc` funziona diversamente, perchè è una finestra su informazioni che il kernel raccoglie.
  
- Un kernel accumula e mantiene informazioni su processi, CPU, memoria e altro; `/proc` ti permette di interrogare quelle informazioni; per esempio, se lanci `cat /proc/meminfo` ti ritrovi informazioni sulla memoria del sistema.

- Le informazioni di cui parliamo sono presentate sotto forma di file e directory, come un filesystem normale, ma sono generate dinamicamente dal kernel invece che archiviate a disco.
  
Per citare un paio di esempi:

- `/proc/cpuinfo`: informazioni sulla CPU.
- `/proc/meminfo`: informazioni sulla memoria.
- `/proc/1234`: informazioni sul processo con PID 1234.
- `/proc/uptime`: tempo trascorso dall'avvio del sistema.

È particolarmente utile per monitoraggio del sistema e troubleshooting.

#### `/run` (Runtime data)
Contiene informazioni temporanee che programmi e servizi hanno bisogno di conservare durante il loro funzionamento (appunto, il runtime).

Facendo un esempio:

- Quando avvii SSH, Linux ha bisogno di conservare temporaneamente alcune informazioni necessarie al suo funzionamento; servono soltanto quando il servizio è in esecuzione, e vengono cancellate e ricreate all'avvio successivo.

- È qui che entra in gioco `/run`, le informazioni possono essere salvate in `/run/sshd`.
  
- I file di cui parliamo vengono scritti in memoria, non su disco, tramite un filesystem chiamato `tempfs`.

Per dirne qualcun'altra:

- `/run/systemd`: sono dati utilizzati da systemd.
- `/run/user/1000`: sono dati runtime della sessione dell'utente con UID 1000.

#### `/srv` (Service data)
Contiene dati forniti dai servizi ospitati dal sistema.

Ad esempio, un server web potrebbe conservare i contenuti di un sito in `/srv/www`, mentre un server FTP potrebbe utilizzare `/srv/ftp`.

L'obiettivo è mantenere separati i dati forniti dai servizi rispetto ai file di configurazione e ai programmi che li gestiscono.

### `/sys` (Kernel and device information)
È un filesystem virtuale, chiamato `sysfs`, che espone informazioni sui dispositivi hardware, sui driver e sulle strutture interne del kernel.

Ad esempio:

- `/sys/class/net`: informazioni sulle interfacce di rete.
- `/sys/block`: informazioni sui dispositivi a blocchi.
- `/sys/devices`: struttura gerarchica dei dispositivi rilevati dal kernel.

È utilizzato dal kernel e dagli strumenti di amministrazione per esporre e gestire informazioni relative all'hardware e ai dispositivi.

### `/tmp` (Temporary files)
Contiene file temporanei creati dalle applicazioni e dagli utenti durante il funzionamento del sistema.

Ad esempio, un programma potrebbe creare un file temporaneo in `/tmp` per conservare dati necessari durante l'esecuzione.

I file presenti in questa directory possono essere eliminati automaticamente durante il riavvio o secondo le politiche di pulizia della distribuzione.

Non bisogna quindi considerarla una posizione adatta alla conservazione permanente dei dati.

### `/usr` (User system resources)
Contiene la maggior parte dei programmi, delle librerie e dei dati condivisi installati nel sistema. Nonostante il nome, non è una directory destinata ai file personali degli utenti.

Alcune directory importanti al suo interno:

- `/usr/bin`: programmi e comandi utilizzabili dagli utenti.
- `/usr/sbin`: strumenti amministrativi.
- `/usr/lib`: librerie e componenti software.
- `/usr/share`: dati indipendenti dall'architettura, come documentazione e file condivisi.
- `/usr/local`: software installato localmente dall'amministratore, al di fuori della gestione ordinaria della distribuzione.

È una delle directory principali del sistema, perché contiene gran parte del software installato.

### `/var` (Variable data)
Contiene dati che cambiano frequentemente durante il funzionamento del sistema, a differenza di quelli generalmente statici presenti in `/usr`.

Alcune directory importanti al suo interno:

- `/var/log`: log del sistema e dei servizi.
- `/var/cache`: dati temporanei utilizzati dalle applicazioni.
- `/var/lib`: dati persistenti utilizzati dai servizi e dalle applicazioni.
- `/var/spool`: dati in attesa di elaborazione, come code di stampa e posta.

È particolarmente importante per il troubleshooting e la manutenzione: ad esempio, analizzando `/var/log` è possibile individuare errori e problemi relativi al funzionamento dei servizi.

---
[[Mount points in Linux]]
[[mount (mount filesystem)]]
[[Soft link]]
[[Hard link]]
[[Everything is a file]]
