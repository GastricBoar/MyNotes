---
date: 2026-03-31
tags:
  - informatica
  - linux
  - pubblico

---
# ext4 (fourth extended filesystem)
---
[[Filesystem]] molto diffuso in [[Linux]], evoluzione di ext3. Viene introdotto nel 2008 da diversi attori della community Linux, con contributi anche da Red Hat e IBM.

### Quali sono le caratteristiche principali?
È pensato per uso generale, con semplicità, performance e stabilità in mente.

### Journaling
Un meccanismo pensato per proteggere la coerenza del filesystem in caso di crash: prima di scrivere blocchi, annota su un journal le operazioni da eseguire. Facendo un esempio:

1. filesystem registra nel journal "seguirò tre step in serie per questa operazione: scrivo dati, aggiorno inode e infine directory"; a serie completata registra un "commit".
2. blackout tra step 2 e step 3.
3. senza journaling potresti ritrovare il filesystem inconsistente.
4. con journaling, il filesystem verifica "quali operazioni son state eseguite? la serie? il commit è stato registrato?"
5. se il commit non è stato registrato, ignora le operazioni precedenti e riporta allo stato coerente.
6. se il commit è stato registrato, le operazioni vengono considerate valide
7. anche a commit registrato, può capitare manchi qualche blocco da scrivere, in quel caso non è un problema farlo per il filesystem.

### Extents
Un meccanismo che ti permette di indicare una serie di blocchi contigui con una sola informazione.

In un filesystem [[FAT (File Allocation Table)]] i blocchi per file vengono indicati singolarmente (es. blocco 100, blocco 101, blocco 102, blocco 103 etc.) mentre in ext4 gli extents ti permettono di indicare più blocchi in una volta sola con un solo record "da blocco 100 a blocco 103".

Fare questo riduce di molto la quantità di metadati da leggere e gestire, perchè se prima servivano 250.000 righe a descrivere un file che occupa 250.000 blocchi, adesso bastano poche righe di extents per fare la stessa cosa; è un accesso più efficiente, meno operazioni di I/O sui metadati.

### Delayed allocation
Rimanda l'allocazione dei blocchi fino al momento della scrittura su disco, in modo che il filesystem possa scegliere aree di blocchi contigui più grandi.

Il filesystem FAT sceglierebbe i blocchi uno a uno, il primo buco libero che trova mentre scrive, tipo "scelgo il blocco 31, poi il 230, poi il 540, poi il 600 etc."

Con la delayed allocation invece:

1. il programma scrive dati
2. il [[Kernel]] non li alloca subito perchè non sa quale sarà la dimensione finale del file, quindi rimanda un attimo
3. li mette temporaneamente in [[Page cache (su RAM)]], il suo buffer temporaneo per operazioni
4. man mano che il file cresce accumula info su quanti dati scrivere, tipo "mi servono 10 mb, mi servono 50 mb, mi servono 200 mb"
5. quando è ora di scrivere può cercare uno spazio contiguo abbastanza grande, invece che scegliere i primo blocchi disponibili

Questo approccio riduce la [[Frammentazione]] e migliora le performance, ma in caso di crash perderesti quei dati scritti in RAM e dovresti ripartire con l'operazione di scrittura.

### Multiblock allocation
Alloca più blocchi insieme, non uno alla volta; migliora performance.

### Scalabilità
File fino a 16 TB, e filesystem fino a 1 EB (1 milione di TB).

### I limiti
Non supporta nativamente compressione, deduplicazione e snapshot; ti servono strumenti esterni.

---
[[Btrfs (B-tree file system)]]