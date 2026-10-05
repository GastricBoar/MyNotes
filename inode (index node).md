---
date: 2026-04-21
tags:
  - informatica
  - linux
  - pubblico

---
# inode (index node)
---
Una struttura dati utilizzata dai [[Filesystem]] per rappresentare file in [[Linux]].

Nel pratico, è un record che:

- identifica il file in maniera univoca all'interno del filesystem (ma solo al suo interno)
- contiene tutte le informazioni su quel file, fatta eccezione per il nome

### Cosa contiene un inode?
Diverse informazioni, tra cui:

- la posizione dei dati sul disco (i blocchi)
- dimensione
- proprietario (owner e suo gruppo)
- permessi
- timestamp vari (quindi accesso, modifica, creazione etc.)

Nota che l'inode non contiene il nome del file: il file è l'inode, il nome è solo un'etichetta poggiata sopra e volendo può averne più di uno (con gli hard links).

Puoi verificare dettagli dell'inode con il comando `stat file.txt` 

In questo contesto le directory sono semplicemente tabelle che associano nome file a un inode.

### Cosa identifica un inode?
Con l'inode number, il suo identificatore univoco all'interno del filesystem; dico "all'interno del filesystem" perchè file appartenenti a filesystem diversi possono avere lo stesso inode number, ma non rappresentano lo stesso file.

Puoi verificare l'inode number di un file con il comando `ls -i`, per fare un esempio:

```
❯ ls -i file.txt

5207516 file.txt
```

### Tutti i sistemi operativi hanno gli inode?
No, i filesystem Linux usano gli inode. 

Apple ha un concetto simile su [[APFS (Apple File System)]], Windows ha qualcosa di simile nella [[MFT (Master File Table)]] di [[NTFS (New Technology File System)]].

---
[[ls (list)]]
[[stat]]