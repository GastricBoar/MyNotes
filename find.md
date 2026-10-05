---
date: 2026-04-27
tags:
  - informatica
  - linux
  - pubblico

---
# find
---
Comando [[Linux]] utilizzato per cercare file e directory all'interno del [[Filesystem]].

### Uso di base
Lanci il comando con la sintassi `find [percorso] [condizione]`

### find -name
Ricerca per nome, case sensitive.

es. `find . -name "Lorem ipsum"`

### find -iname (ignore name)
Ricerca per nome, ignora maiuscole e minuscole.

### find -type
Filtra per file (f) o directory (d).

es. `find . -type f`

### find -size
Filtra per dimensione.

es.  `find . -size +100M` 
es.  `find . -size -30M` 
es.  `find . -size 40M` 

### find -user
Filtra per utente a cui appartiene.

es.  `find . -user steve` 

### find -mtime (modified time)
Filtra per data di ultima modifica.

es.  `find . -mtime +1` 
es.  `find . -type f -mtime -2` 

### find -exec (execute)
Esegue un comando, `{}` rappresenta ogni oggetto trovato e `\;` chiude il comando exec.

es.  `find . -type f -name "*.log" -exec rm -f {} \;` 

---
[[grep (Global Regular Expression Print)]]


