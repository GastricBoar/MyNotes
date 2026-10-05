---
date: 2026-04-29
tags:
  - informatica
  - linux
  - pubblico

---
# ps (process status)  
---  
Un comando [[Linux]] utilizzato per visualizzare i processi in esecuzione.

A differenza di [[top (top processes)]], `ps` non monitora in tempo reale, ma scatta una singola fotografia istantanea; se `top` è pensato per monitorare, `ps` è pensato per interrogare.
  
### Uso di base  
Lanci il comando con la sintassi `ps`

Lanciare il comando con questa sintassi non è troppo comune: vedresti solo i processi nati a partire da quella sessione di terminale; Firefox però ti capita di averlo aperto da DE, quindi non lo vedresti.

### ps aux
Cattura una fotografia di tutti i processi attivi a sistema, inclusi quelli senza terminale.

Usa sintassi storica BSD-style, nello specifico:
- `a` sta per "all users with TTY", e mostra i processi di tutti gli utenti
- la `u` sta per "user-oriented format"
- la `y` sta per "include processes without TTY", per includere processi senza terminale

### ps -ef
Anche lui cattura processi attivi e gerarchia tra loro, molti lo preferiscono a `ps aux`.

La sintassi arriva da [[System V]], e nello specifico:

- `e` sta per "every process"
- `f` sta per "full format"

### ps -p (process)
Ti dà informazioni su uno specifico processo.

Lo lanci con la sintassi `ps -p [PID]`

es. `ps -p 2481`

### ps -u (user)
Ti dà informazioni sui processi in attivo su uno specifico utente.

Lo lanci con la sintassi `ps -u [utente]`

es. `ps -p mario`

### ps -eo 
Mostra una tabella di processi, ma puoi personalizzare le colonne che la compongono.

Lo lanci con la sintassi `ps -eo [colonne],[della],[tabella]`

es. `ps -eo pid,user,%cpu,%mem,cmd`

### ps -ef --forest 
Visualizza i processi ad albero, così puoi capire la gerarchia padre-figlio tra processi.

### Per cosa lo uso?
Ci sono tanti scenari in cui ti è utile.

### Terminare un singolo processo
Mettiamo tu voglia ritrovare il PID di un processo, per poterlo terminare.

Lancia `ps aux | grep firefox` oppure molto più pulito `ps -C firefox`, poi dal PID ricavato lanci `kill 2481`

### Verificare lo stato di un processo
Vuoi capire se un processo è in esecuzione o meno, stesso comando di prima.

### Verificare la gerarchia di un processo
Con `ps -ef --forest` come visto prima.

### Verificare l'utilizzo di risorse 
Con vari filtri e ordinamenti in base alla sintassi che utilizzi, ma facciamo un esempio: vuoi capire quali processi stanno usando più RAM.

Lanceresti `ps aux --sort=-%mem | head`

### Un fun fact :)
`ps` è uno dei pochi comandi Linux moderni che supporta contemporaneamente sintassi storiche diverse (BSD, System V/POSIX e GNU), motivo per cui sia `ps aux` che `ps -ef` funzionano anche se seguono convenzioni nate in famiglie UNIX rivali decenni fa.

L'intenzione è quella di mantenere compatibilità con sistemi vecchissimi, per quei sysadmin che li usano; `ps` è un dinosauro UNIX.

---
[[TTY (Teletypewriter)]]