---
date: 2026-07-06
tags:
  - informatica
  - linux
  - pubblico

---
# man (Manual)
---
Comando [[Linux]] utilizzato per leggere il manuale di comandi e altri componenti di sistema.

### Come è strutturato?
Il manuale è diviso in sezioni, e ciascuna categoria è dedicata a una specifica categoria di documentazione:

| Sezione | Contenuto                                |
| ------: | ---------------------------------------- |
|       1 | Comandi utente                           |
|       2 | Chiamate di sistema (System Calls)       |
|       3 | Funzioni di libreria                     |
|       4 | File speciali e dispositivi              |
|       5 | Formati di file e file di configurazione |
|       6 | Giochi                                   |
|       7 | Convenzioni, standard e miscellanea      |
|       8 | Comandi di amministrazione               |

Se vuoi aprire una pagina appartenente a una specifica sezione, ne indichi il numero; ad esempio: 
  
```bash  
man 5 passwd  
```  
  
apre la documentazione del file `/etc/passwd`, mentre:  
  
```bash  
man 1 passwd  
```  
  
apre la documentazione del comando `passwd`.


### Visualizzare il manuale di un comando
Lanci il comando con la sintassi `man [comando]`

es.

```bash
man ls
```

### Cercare una parola all'interno del manuale
Una volta aperta una pagina, premi:

```text
/parola
```

e premi `Invio`.

Per passare al risultato successivo premi:

```text
n
```

### man -k (Keyword)

Cerca tutti i manuali che contengono una determinata parola chiave.

Lanci il comando con la sintassi:

```bash
man -k network
```

### man -f (Whatis)
Mostra una breve descrizione del comando, è un frontend per il comando [[whatis]]

Lanci il comando con la sintassi:

```bash
man -f ls
```

### Le sezioni POSIX  
Alcuni comandi hanno una pagina appartenente alle sezioni POSIX, indicate con il suffisso `p` (ad esempio `1p`).  
  
Ad esempio:  
  
```bash  
man 1 ls  
```  
  
apre la documentazione del comando `ls` installato sul sistema (ad esempio quello fornito da GNU Coreutils).  
  
```bash  
man 1p ls  
```  
  
apre invece la documentazione dello stesso comando conforme allo standard POSIX.  
  
Le pagine POSIX descrivono soltanto il comportamento garantito dallo standard POSIX, mentre le pagine "normali" possono includere funzionalità aggiuntive specifiche dell'implementazione GNU Coreutils.

Le pagine POSIX sono utili quando sviluppi script che devono essere compatibili con diversi sistemi Unix-like (es. FreeBSD, macOS, Solaris etc.)

---