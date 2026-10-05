---
date: 2026-07-06
tags:
  - informatica
  - linux
  - pubblico

---
# cat (Concatenate)
---
Comando [[Linux]] utilizzato per visualizzare, concatenare e creare file di testo.

Nonostante il nome "concatenare", nella pratica viene utilizzato soprattutto per visualizzare rapidamente il contenuto di un file.

Per visualizzare file di grandi dimensioni è generalmente preferibile usare `less`, che ti permette di scorrere il contenuto in maniera interattiva.

### Visualizzare il contenuto di un file
Lanci il comando con la sintassi `cat [file]`

es.

```bash
cat file.txt
```

oppure, per visualizzare più file uno dopo l'altro:

```bash
cat file1.txt file2.txt
```

### Concatenare più file in uno nuovo
Lanci il comando con la sintassi `cat [file1] [file2] > [file_destinazione]`

es.

```bash
cat parte1.txt parte2.txt > completo.txt
```

### Creare un file

Lanci il comando con la sintassi `cat > [file]`

es.

```bash
cat > note.txt
```

Scrivi il contenuto desiderato e premi `Ctrl + D` per salvare il file.

### cat -n (Number)
Mostra il contenuto del file numerando tutte le righe.

Lanci il comando con la sintassi:

```bash
cat -n file.txt
```

### cat -b (Number Non-Blank)
Numera soltanto le righe non vuote.

Lanci il comando con la sintassi:

```bash
cat -b file.txt
```

---
