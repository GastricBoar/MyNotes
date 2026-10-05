---
date: 2026-04-26
tags:
  - informatica
  - linux
  - pubblico

---
# grep (Global Regular Expression Print)
---
Comando [[Linux]] utilizzato per cercare testo all'interno di file, directory e output.

### Uso di base
Lanci il comando con la sintassi `grep [testo] [file]`

es. `grep "Doggos" file.txt`
es. `grep "Doggos" file1.txt file2.txt`

### grep -i (ignore case)
Ignora il controllo di maiuscole e minuscole.

### grep -r (recursive)
Partendo da una directory, cerca testo all'interno di tutte le sottodirectory.

Lanci il comando con la sintassi `grep -r "Lorem ipsum" Downloads/`

es. `grep -r "Lorem ipsum" Downloads/`
es. `grep -r "Doggos" .`

### grep -n (number)
Riporta numero di linea accanto alla ricerca eseguita.

### grep -c (count)
Conta il numero di occorrenze per il testo cercato.

### grep -l (list files)
Riporta elenco dei file che contengono il pattern.

### grep -v (invert match)
Mostra le righe che non contengono il pattern.

---
[[find]]