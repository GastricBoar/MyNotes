---
date: 2026-04-23
tags:
  - informatica
  - linux
  - pubblico

---
# cp (copy)
---
Comando [[Linux]] utilizzato per copiare file e directory.

### Copiare un file
Lanci il comando con la sintassi `cp [file] [dir destinazione]`

es. `cp file.txt /home/daniele/Documents/`

### Copiare e rinominare un file
Lanci il comando con la sintassi `cp [file] [dir destinazione]/[file rinominato]`

es. `cp file.txt /home/daniele/Documents/doggo.txt`

### Copiare una directory
Lanci il comando con la sintassi `cp -r [directory] [dir destinazione]`

es. `cp -r doggos/ /home/daniele/Documents/`

Quell'`r` sta per ricorsivo.

> Attenzione, perchè se un file chiamato così esiste già, il comando lo sovrascrive senza chiedere.

### cp -i (interactive)
Chiede prima di sovrascrivere.

### cp -n (no-clobber)
Se il file esiste già, non sovrascrive nulla.

### cp -v (verbose)
Mostra le operazioni in corso.

### cp -iv (verbose)
Chiede prima di sovrascrivere, e mostra le operazioni in corso.

---
[[mv (Move)]]
