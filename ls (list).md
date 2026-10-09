---
date: 2026-04-21
tags:
  - informatica
  - linux
  - pubblico

---
# ls (list)
---
Un comando [[Linux]] che elenca file e directory.

Nel suo uso base con `ls` mostra il contenuto della directory selezionata, ma ha poi una serie di flag che ne estendono le funzioni.

### ls -l
Elenca in maniera dettagliata il contenuto della directory selezionata:

```
$ ls -l

-rw-r--r-- 1 daniele devgroup 0 18 apr 15.47 file.txt
drwxr-xr-x 1 daniele devgroup 0 18 apr 15.47 mydirectory
```

Il formato di questo output è:

```
[permessi][n. hard links] [owner] [group] [dimensione in byte] [data] [nome file]
```

### Altri flag utili
Un paio:

```
ls -a    # includi file nascosti
ls -la   # dettagli e file nascosti
ls -lh   # dimensioni leggibili (non in byte)
ls -i    # mostra inode number
ls -ld   # info sulla directory, non sul contenuto
```

---
[[Bit (Binary digit)]]
[[Hard link]]
[[inode (index node)]]