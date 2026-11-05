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
È un filesystem virtuale che espone informazioni sui processi in esecuzione e sullo stato delle risorse gestite dal kernel. Quando dico "filesystem virtuale" intendo che:

- Normalmente, quando apri un file, leggi informazioni che qualcuno ha già salvato a disco.
  
- Le informazioni di cui abbiamo parlato sopra sono presentate sotto forma di file e directory, come un filesystem normale, ma sono generate dinamicamente dal kernel invece che archiviate a disco.
  
Un kernel accumula e mantiene informazioni sullo stato di processi, CPU, memoria e altro; `/proc` è una finestra su queste informazioni, e ti permette di interrogarle; per esempio, se lanci `cat /proc/meminfo` ti ritrovi informazioni sull'utilizzo della RAM.
  
Per citare qualche altro esempio:
- `/proc/cpuinfo`: informazioni sullo stato della CPU.
- `/proc/1234`: informazioni sul processo con PID 1234.
- `/proc/uptime`: tempo trascorso dall'avvio del sistema.

È particolarmente utile per monitoraggio del sistema e troubleshooting, e non è da confondere con `/sys`:

- Entrambi espongono informazioni del kernel.
  
- `/proc` espone principalmente informazioni sullo stato del sistema e dei processi, risponde alla domanda "cosa sta succedendo adesso nel sistema?".
  
- `/sys` espone informazioni su dispositivi hardware, driver e la loro gestione da parte del kernel, risponde alla domanda "quali dispositivi son presenti e come vengono gestiti?".

Ci sono delle aree di sovrapposizione, non è una separazione assoluta.

#### `/run` (Runtime data)
Contiene informazioni temporanee che programmi e servizi hanno bisogno di conservare durante il loro funzionamento (appunto, il runtime).

Facendo un esempio:

- Quando avvii SSH, Linux ha bisogno di conservare temporaneamente alcune informazioni necessarie al suo funzionamento; servono soltanto quando il servizio è in esecuzione, e vengono cancellate e ricreate all'avvio successivo.

- È qui che entra in gioco `/run`, le informazioni possono essere salvate in `/run/sshd`.
  
- I file di cui parliamo vengono scritti in memoria, non su disco, tramite un filesystem virtuale chiamato `tempfs`.

Per dirne qualcun'altra:

- `/run/systemd`: sono dati utilizzati da systemd.
- `/run/user/1000`: sono dati runtime della sessione dell'utente con UID 1000.

#### `/srv` (Serve data)
Contiene i dati che i servizi mettono a disposizione (appunto "servono") di altri computer e utenti in rete.

Per fare un esempio: un web server potrebbe conservare i contenuti di un sito in `/srv/www`, mentre un server FTP potrebbe conservarli `/srv/ftp`.

L'obiettivo è separare:
- I dati che un servizio fornisce ad altri computer e utenti.
- Dai file di configurazione del servizio in sè.

### `/sys` (Kernel and device information)
Utilizzato dal kernel per esporre informazioni su dispositivi hardware, driver e la loro gestione.

Come visto in `/proc` e `/run`, anche questa directory usa filesystem virtuale per immagazzinare dati, si chiama `sysfs`.

Un paio di esempi:

- `/sys/class/net`: informazioni sulle interfacce di rete.
- `/sys/block`: informazioni sui dispositivi a blocchi.
- `/sys/devices`: struttura ad albero dei dispositivi rilevati dal kernel.

Per come dicevamo prima, non è da confondere con `/proc`:

- Entrambi espongono informazioni del kernel.
  
- `/proc` espone principalmente informazioni sullo stato del sistema e dei processi, risponde alla domanda "cosa sta succedendo adesso nel sistema?".
  
- `/sys` espone informazioni su dispositivi hardware, driver e la loro gestione da parte del kernel, risponde alla domanda "quali dispositivi son presenti e come vengono gestiti?".

Ci sono delle aree di sovrapposizione, non è una separazione assoluta.

### `/tmp` (Temporary files)
Contiene file temporanei creati dalle applicazioni e dagli utenti durante il funzionamento del sistema.

Ad esempio, un programma potrebbe creare un file temporaneo in `/tmp` per conservare dati necessari durante l'esecuzione.

I file presenti in questa directory possono essere eliminati automaticamente durante il riavvio o secondo le politiche di pulizia della distribuzione.

Non bisogna quindi considerarla una posizione adatta alla conservazione permanente dei dati.

### `/usr` (User system resources)
Contiene la maggior parte dei programmi e delle librerie installati a sistema. Nonostante il nome, non è una directory destinata ai file personali degli utenti.

Per capire meglio, alcune directory importanti al suo interno:

- `/usr/bin`: contiene la maggior parte dei programmi e dei comandi utilizzabili dagli utenti.
  
- `/usr/sbin`: contiene gli strumenti amministrativi.
  
- `/usr/lib`: contiene librerie e componenti condivise utilizzati dai programmi, parliamo di codice qui.
  
- `/usr/share`: contiene risorse dei programmi che a differenza di `/lib` non sono codice eseguibile; cose come documentazione, icone, traduzioni, template e altro.
  
- `/usr/local`: contiene il software installato localmente dall'amministratore, quello al di fuori della gestione ordinaria dei pacchetti della distribuzione.

Fai attenzione, perchè nelle distribuzioni Linux moderne che adottano il modello usr-merge, le directory storicamente separate come `/bin`, `/sbin` e `/lib` sono diventate collegamenti simbolici verso le rispettive directory sotto `/usr`: `/bin` diventa `/usr/bin`, `/sbin` diventa `/usr/sbin`,  `/lib` diventa `/usr/lib` e così via.

Con i link simbolici, i file sono fisicamente organizzati sotto `/usr`, ma i vecchi percorsi continuano comunque a funzionare per compatibilità.

### `/var` (Variable data)
Contiene dati che cambiano frequentemente durante il funzionamento di sistema e servizi, appunto dati variabili. 

Attenzione che parliamo di dati variabili, non per forza temporanei: a differenza dei dati generalmente statici di programmi e file di configurazione, questi dati cambiano frequentemente perchè creati e aggiornati in continuazione durante l'esecuzione del sistema.

Alcune directory importanti:

- `/var/log`: log del sistema e dei servizi.
  
- `/var/cache`: dati temporanei utilizzati dalle applicazioni.
  
- `/var/lib`: dati persistenti utilizzati dai servizi e dalle applicazioni, es. il database di un'applicazione può essere conservato qui; come dicevamo su, è il perfetto esempio di un dato variabile ma non temporaneo.
  
- `/var/spool`: dati in attesa di elaborazione, come code di stampa e posta.

È una directory importante per troubleshooting e manutenzione: ad esempio, analizzando `/var/log` è possibile individuare errori e problemi relativi al funzionamento dei servizi.

---
[[Mount points in Linux]]
[[mount (mount filesystem)]]
[[Soft link]]
[[Hard link]]
[[Everything is a file]]
[[etc (Et Cetera)]]
[[/var]]
[[/usr]]
[[/usr]]
