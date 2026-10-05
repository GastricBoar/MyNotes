---
date: 2026-06-15
tags:
  - informatica
  - linux
  - pubblico

---
# tar (tape archive)

---
Comando [[Linux]] utilizzato per creare, visualizzare ed estrarre archivi di file e directory.

Di per sé non comprime i dati, ma può integrarsi con programmi di compressione come gzip e xz.

### tar cvf (create, verbose, file)
Crea un archivio, verbosamente.

Lanci il comando con la sintassi `tar cvf [archivio] [file/cartelle]`

es. `tar cvf backup.tar Documenti/`  
es. `tar cvf backup.tar file1.txt file2.txt`

### tar tvf (table, verbose, file)

Mostra il contenuto di un archivio senza estrarlo.

es. `tar tvf backup.tar`  
es. `tar tf backup.tar`

### tar xvf (extract, verbose, file)
Estrae il contenuto di un archivio.

es. `tar xvf backup.tar`

### tar czvf (create, gzip, verbose, file)
Crea un archivio compresso con gzip.

es. `tar czvf backup.tar.gz Documenti/`  
es. `tar czvf etc_backup.tar.gz /etc`

### tar xzvf (extract, gzip, verbose, file)
Estrae un archivio compresso con gzip.

es. `tar xzvf backup.tar.gz`

### tar cJvf (create, xz, verbose, file)
Crea un archivio compresso con xz.

es. `tar cJvf backup.tar.xz Documenti/`

### tar xJvf (extract, xz, verbose, file)
Estrae un archivio compresso con xz.

es. `tar xJvf backup.tar.xz`

### tar -C (change directory)
Estrae l'archivio in una directory specifica.

es. `tar xzvf backup.tar.gz -C /tmp/restore`

---