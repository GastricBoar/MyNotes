---
date: 2026-05-11
tags:
  - informatica
  - linux
  - pubblico

---
# du (disk usage)
---
Comando [[Linux]] utilizzato per verificare la quantità di spazio a disco occupata da uno specifico file o directory.

Non è da confondere con [[df (disk free)]], che stima la quantità di spazio libero a disco, e non da oggetti specifici.

### du -h 
Mostra lo spazio occupato da ciascuna directory all'interno del percorso scelto; alla fine, include il totale per la directory corrente. A schermo non vengono visualizzati file singoli, solo directory.

```
80M     ./Compleanno
24K     ./Note
8,2G    .
```

`h` sta per "human readable".

Lanci il comando con la sintassi `du -h [percorso]`

### du -ah
Mostra lo spazio occupato da file, directory e file dentro directory per il percorso scelto; alla fine, include il totale per la directory corrente.

```
1M     ./Compleanno/auguri.txt
79M     ./Compleanno/video.mp4
24K     ./Note/Switch.md
36K     ./Note/Router.md
8,0G    ./windows.iso
8,2G    .
```

`h` sta per "human readable", `a` sta per "all"

Lanci il comando con la sintassi `du -ah [percorso]`

### du -sh
Mostra solo il totale dello spazio occupato per il percorso scelto.

```
8,2G    /home/user/Downloads
```

`h` sta per "human readable", `s` sta per "summarize"

Lanci il comando con la sintassi `du -sh [percorso]`

### du -sh *
Mostra il totale di spazio occupato da ciascun file e ciascuna directory e file per il percorso scelto. In output è più pulito di `du -ah` come vedi:

```
80M     Compleanno
24K     Note
8,0G    windows.iso
```

Lanci il comando con la sintassi `du -sh [percorso]`


---
