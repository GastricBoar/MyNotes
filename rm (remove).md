---
date: 2026-04-25
tags:
  - informatica
  - linux
  - pubblico

---
# rm (remove)
---
Comando [[Linux]] utilizzato per eliminare file e directory.

### Eliminare un file
Lanci il comando con la sintassi `rm [file]`

es. `rm file.txt`

### Eliminare una directory
Lanci il comando con la sintassi `rm -r [directory]`

es. `rm -r /home/daniele/Documents/doggos/`

Quell'`r` sta per ricorsivo.

### rm -i (interactive)
Chiede prima di eliminare.

### rm -f (force)
Rimuove forzatamente, ignorando errori e dialog vari.

Per fare due esempi:

- se provi a rimuovere un file inesistente, ricevi un errore a schermo; `rm -f` bypassa questo comportamento.
- se provi a rimuovere un file non scrivibile, ricevi un avviso di conferma "rimuovere il file protetto?"; `rm -f` lo forza senza chiederti nulla.

### rm -v (verbose)
Mostra le operazioni in corso.

### rm -rf 
Elimina directory e contenuto forzatamente.

---
[[mv (Move)]]
