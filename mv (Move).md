---
date: 2026-04-23
tags:
  - informatica
  - linux
  - pubblico

---
# mv (Move)
---
Comando [[Linux]] utilizzato per spostare o rinominare file e directory.

### Spostare un file
Lanci il comando con la sintassi `mv [file] [dir destinazione]`

es. `mv file.txt /home/daniele/Documents/`

### Rinominare un file
Lanci il comando con la sintassi `mv [file] [file rinominato]`

es. `mv file.txt doggo.txt`

### Spostare e rinominare un file
Lanci il comando con la sintassi `mv [file] [dir destinazione]/[file rinominato]`

es. `mv file.txt /home/daniele/Documents/doggo.txt`

> Attenzione, perchè se un file chiamato così esiste già, il comando lo sovrascrive senza chiedere.

### Spostare una directory
Lanci il comando con la sintassi `mv [directory] [dir destinazione]`

es. `mv doggos/ /home/daniele/Documents/`

### mv -i (interactive)
Chiede prima di sovrascrivere.

### mv -n (no-clobber)
Se il file esiste già, non sovrascrive nulla.

### mv -v (verbose)
Mostra le operazioni in corso.

### mv -iv (verbose)
Chiede prima di sovrascrivere, e mostra le operazioni in corso.

---
[[cp (copy)]]