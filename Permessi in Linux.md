---
date: 2026-04-18
tags:
  - linux
  - informatica
  - pubblico

---
# Permessi in Linux
---
Regolano accesso alle risorse, dicono chi può fare cosa e dove.

Per visualizzare al volo i permessi imposti su un oggetto lanci il comando `ls -l

### Come esamino i permessi di un oggetto?
In tre modi diversi:

- usi `ls -l` se vuoi esaminare tutti i permessi dentro una specifica directory
  
- usi `ls -l file.txt`  se vuoi esaminare i permessi di un singolo file
  
- usi `ls -ld mydirectory` se vuoi esaminare i permessi di una directory (non del contenuto)

### Come sono strutturati i permessi?
Facciamo un esempio:

```
$ ls -l

-rw-r--r-- 1 daniele devgroup 0 18 apr 15.47 file.txt
drwxr-xr-x 1 daniele devgroup 0 18 apr 15.47 mydirectory
```

guarda la stringa dei permessi a inizio riga, è composta da 10 caratteri:

- il primo carattere specifica il tipo di oggetto (`-` è un file, `d` una directory, `l` un link simbolico)
  
- seguono tre gruppi da tre cifre ciascuna: permessi per il proprietario (user), permessi per il gruppo (group), permessi per tutti gli altri (others).

<img src="Utilities/Media/Pasted%20image%2020260418155340.png" alt="Pasted image 20260418155340.png" width="419">

### Read, write e execute
Tre permessi che ti permettono di stabilire regole, lo fanno in modo diverso per file o directory:

- **con read (r) leggi:** su un file ne leggi il contenuto; su una directory ne listi i file, ma senza `x` non puoi entrare in directory
  
- **con write (w) scrivi:** su un file ne modifichi il contenuto; su una directory crei ed elimini file

- **con execute (x) esegui:** su un file lo esegui (es. uno script); su una directory ci entri dentro (con `cd`) ma senza `r` non puoi vedere cosa contiene, se conosci già il nome di un file puoi comunque accedervi (es. `cat dir/file.txt`)

### Permessi in formato simbolico
Puoi rappresentare i permessi Linux in formato simbolico, quindi:

- **ogni permesso è rappresentato da una lettera:** read è `r`, write è `w`, execute è `x`
- **la combinazione delle lettere definisce il permesso assegnato:** es. `rwx` indica read, write ed execute
- **un set di 3 gruppi definisce owner, group e others:** es. `rwxrwxrwx` assegna tutti i permessi a tutti
- **il simbolo `-` indica assenza di permesso:** es. `rw-r--r--` significa che solo l’owner può scrivere, mentre gli altri possono solo leggere

### Permessi in formato numerico
Oltre la "modalità simbolica" vista prima, puoi rappresentare i permessi Linux in chiave numerica, quindi:

- **ad ogni permesso assegni un numero:** read è 4, write è 2, execute è 1

- **la somma dei numeri definisce il permesso assegnato:** es. 7 è read, write ed execute

- **un set di 3 permessi definisce owner, group e others:** es. 777 definisce permesso rwx per tutti quanti

### Come assegno permessi?
Con [[chmod (change mode)]], seguendo la sintassi `chmod [permessi] [nomefile`], ma anche qui puoi assegnare i permessi in diversi modi:

- **In formato simbolico relativo, aggiunge il permesso di scrittura al gruppo e modifica solo ciò che specifichi:**
  
```
chmod g+w file.txt
  
chmod o-r,g+r file.txt
  
chmod u+x script.sh
```
  
- **In formato simbolico assoluto, imposta esattamente quei permessi sovrascrivendo i precedenti:**
  
```
chmod u=rw,g=r,o= file.txt

chmod u=rwx,g=rx,o=rx script.sh

chmod u=rw file.txt
```
  
- **In formato numerico, imposta esattamente quei permessi sovrascrivendo i precedenti:**

```
chmod 644 file.txt

chmod 755 script.sh

chmod 700 private.sh
```

---
[[ls (list)]]