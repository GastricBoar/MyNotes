---
date: 2026-05-01
tags:
  - informatica
  - linux
  - pubblico

---
# top (top processes)
---
Un comando [[Linux]] usato per monitorare processi e risorse di sistema. Il nome deriva da "top processes", i processi più attivi e pesanti in alto.  
### Uso di base  
Lanci il comando con `top` e basta.  
  
### Come funziona?  
A lanciare il comando ti trovi davanti una schermata divisa in due sezioni principali.  
  
### La sezione in alto  
Ti mostra una panoramica dello stato di sistema:  
  
![Pasted image 20260503214034.png](Utilities/Media/Pasted%20image%2020260503214034.png)  
  
**In riga 1 vedi:**  
  
```
top - 21:40:10 up 10:05, 1 user, load average: 0,84, 0,45, 0,28
```

- `21:40:10` è l'ora attuale  
    
- `up 10:05` è l'uptime in formato HH:MM  
    
- `1 user` il numero di utenti loggati  
    
- `load average: 0,84, 0,45, 0,28` ti indica il carico medio rispetto alla capacità della CPU negli ultimi 1, 5 e 15 minuti. Per interpretarlo correttamente lo devi rapportare al numero di core del tuo processore: se hai una CPU a due core e il carico è 0.28 stai tranquillo, se è a 2.0 sei a pieno carico, se è a 4.0 sei in overload e alcuni processi stanno aspettando in coda.  
  
**In riga 2 vedi:**  

```
Tasks: 441 total, 1 running, 440 sleeping, 0 d-sleep, 0 stopped, 0 zombie
```

- `441 total, 1 running, 440 sleeping` sono in ordine processi totali, processi attualmente attivi sulla CPU e processi che invece non la stanno utilizzando al momento (es. Firefox in sottofondo ma non lo stai usando)  
    
- `0 d-sleep` sta per "uninterruptible sleep", sono processi in attesa di qualcosa, e non interrompibili; spesso sono processi in attesa di operazioni I/O, come accessi al disco, alla rete o ad altri dispositivi.  
  
- `0 stopped` sono i processi che hai sospeso manualmente, non utilizzano CPU fin quando son congelati.  
    
- `0 zombie` sono processi morti ma non ancora rimossi dalla tabella dei processi, es. processo figlio ha finito di lavorare ma il processo padre per qualche motivo non riesce a leggerne lo stato; non occupano CPU o risorse, ma se diventano molti è da indagare un problema software  
    
**In riga 3 vedi:**  
  
```
%Cpu(s): 2,3 us, 0,5 sy, 0,0 ni, 85,4 id, 11,5 wa, 0,2 hi, 0,1 si, 0,0 st
```

  - `%Cpu(s)` è la percentuale di CPU utilizzata, aggregando tutti i core invece che mostrarli singolarmente; "s" è una notazione storica di top, ma per ricordare puoi credere sia "s" di "system-wide".

  - `2,3 us` (user) è la CPU usata dai programmi utente (browser, editor, giochi etc.)

  - `0,5 sy` (system) è la CPU utilizzata dal [[Kernel]], per cose tipo gestione memoria, driver, gestione file etc.

  - `0,0 ni` (nice) è la CPU utilizzata da processi con priorità non standard (diversa da 0); il parametro "nice" indica quanto un processo è "nice" verso gli altri, ovvero quanta CPU è disposto a lasciar loro prima di usarla lui stesso. È un valore che va da -20 (massima priorità) a +19 (minima priorità) passando per 0 (priorità standard), lo puoi modificare tu manualmente o il sistema (es. un gioco, un processo audio, un backup o una compressione file).

- `85,4 id` (idle) è la CPU attualmente libera.
  
- `11,5 wa` (iowait) è la CPU ferma ad aspettare operazioni I/O dal disco, es. copi un file grande e la CPU resta ferma fin quando aspetta il disco; più sale più è lento o complesso il lavoro fatto dal disco.
  
- `0,2 hi` (hardware interrupt) è la CPU utilizzata per gestire hardware (mouse, tastiera, rete, periferiche varie); un "interrupt" è un segnale che interrompe temporaneamente la CPU, perchè quando un dispositivo fisico ti chiede qualcosa è come dicesse "ehi CPU, guarda qui!"; esempi di questo sono il click di un tasto, un pacchetto di rete in arrivo, un disco che ha concluso un'operazione etc.
  
- `0,1 si` (software interrupt) è la CPU utilizzata per gestire eventi software urgenti notificati al kernel; a differenza di sy, non è rappresentato dal lavoro ordinario del kernel (es. filesystem, memoria, processi), ma da operazioni che al kernel tocca gestire subito (es. rete, I/O o driver); tutto l'interrupt è lavoro del kernel, ma non tutto il lavoro del kernel è interrupt.
  
- `0,0 st` (steal) riguarda ambienti virtualizzati; se sei in VM, è la quantità di CPU che l'host utilizza al posto tuo.

**In riga 4 vedi:**  

```
MiB Mem : 31634,2 total, 641,3 free, 11970,3 used, 19505,4 buff/cache
```

- `MiB Mem` indica la quantità di RAM in Mebibyte (1024 x 1024 byte invece che 1000 x 1000 come nei MB); se vuoi approfondire, leggi [[KB e KiB (Kilobyte e Kibibyte)]]
  
- `31634,2 total` è la RAM totale disponibile a sistema.
  
- `641,3 free` è la RAM completamente libera e inutilizzata; attenzione perchè poca RAM libera non è automaticamente simbolo di un problema, viene utilizzata in altro invece che esser sprecata.
  
- `11970,3 used` è la RAM utilizzata attualmente da programmi, processi e kernel.
  
- `19505,4 buff/cache` è la RAM utilizzata da sistema per cache, buffer e ottimizzazioni varie. Per fare un esempio, se apri un file grosso Linux lo tiene in cache RAM per velocizzarne l'avvio alla prossima apertura, è un buon modo di utilizzarla invece che sprecarla; se poi quella RAM serve a programmi, la libera automaticamente dalla cache senza problemi.
  
**In riga 5 vedi:**  

```
MiB Swap: 15566,0 total, 15566,0 free, 0,0 used. 19663,9 avail Mem
```

- `MiB Swap` indica la quantità di spazio a disco usato come memoria [[Swap]], in Mebibyte.
  
- `15566,0 total` è lo spazio di swap totale disponibile a sistema.
  
- `15566,0 free` è lo spazio di swap attualmente libero.
  
- `0,0 used` è lo spazio di swap utilizzato.
  
- `19505,4 buff/cache` è memoria RAM che il sistema pensa di poter utilizzare prima di dover ricorrere a spazio su swap; grossolanamente, è la somma di quel `641,3 free` e di `19505,4 buff/cache`, ma devi togliere un a piccola quantità di RAM che il kernel vuole riservarsi.

### La sezione in basso
Ci trovi una tabella di processi attivi a sistema, con varie informazioni.

![Pasted image 20260507211911.png](Utilities/Media/Pasted%20image%2020260507211911.png)

- `PID` (process id) è l'identificativo del processo.
  
- `USER` è l'utente proprietario del processo (es. mario o root).
  
- `PR` (priority) è la priorità del processo, ed è diversa dal valore nice; quello è un suggerimento che l'utente o il sistema dà al kernel, influenza il valore pr finale calcolato dal kernel, ma non la imposti direttamente. Il valore pr va da 0 a 139, ma in top ne vedi una versione semplificata.
  
- `NI` (nice) indica quanto un processo è "nice" verso gli altri, ovvero quanta CPU è disposto a lasciar loro prima di usarla lui stesso. È un valore che va da -20 (massima priorità) a +19 (minima priorità) passando per 0 (priorità standard), lo puoi modificare tu manualmente o il sistema (es. un gioco, un processo audio, un backup o una compressione file).
  
- `VIRT` (virtual memory) è la quantità totale di memoria virtuale allocata per quel processo, ed è volutamente enorme, guarda quella cazza di app Electron che se ne sta prendendo 1400 GB; non è RAM realmente utilizzata, solo un grosso spazio di indirizzi virtuali che i programmi si riservano per organizzare memoria, librerie, allocazioni e altro senza chiedere continuamente al kernel altra memoria.

- `RES` (resident memory) è la quantità di RAM fisica utilizzata dal processo, in byte; premendo  `E` sulla tastiera cicli tra KB, MB, GB etc.

- `SHR` (shared memory) è la RAM condivisa tra più processi; se diverse applicazioni utilizzano una certa libreria, tanto vale condividere componenti comuni per risparmiare RAM.

- `S` (state) è lo stato del processo: R (running), S (sleep), D (ininterruptible sleep), T (stopped), e Z (zombie).
  
- `%CPU` è la quantità di CPU che il processo occupa rispetto a un singolo core; i valori sono da intendersi in relazione al numero di core totali, quindi 400% CPU significa che hai 4 core saturi.
  
- `%MEM` è la percentuale di RAM utilizzata in rapporto al totale (es. 17%).
  
- `TIME+` è il tempo totale di CPU consumato dal processo; non è tempo reale, ma solo il tempo per il quale il processo usa CPU (es. PC aperto da ore, ma un processo potrebbe avere 12 secondi addosso se è rimasto inattivo).
  
-  `COMMAND` è il nome del processo.

### Come si usa?
Premere dei tasti su tastiera ti permette di fare diverse cose:

| Tasto   | Cosa fa                         | Descrizione                                                    |
| ------- | ------------------------------- | -------------------------------------------------------------- |
| `P`     | Sort CPU                        | Ordina i processi per `%CPU` (più CPU sopra).                  |
| `M`     | Sort Memory                     | Ordina per `%MEM` / `RES` (più RAM sopra).                     |
| `R`     | Reverse sort                    | Inverte l’ordinamento corrente.                                |
| `q`     | Quit                            | Esce da `top`.                                                 |
| `k`     | Kill process                    | Invia un segnale a un processo (`SIGTERM` di default).         |
| `/`     | Search                          | Cerca un processo per nome.                                    |
| `T`     | Sort Time                       | Ordina per `TIME+` (tempo CPU totale accumulato).              |
| `c`     | Toggle command line             | Mostra il comando completo invece del solo nome processo.      |
| `N`     | Sort PID                        | Ordina per PID.                                                |
| `b`     | Bold toggle                     | Evidenzia processi attivi/in uso CPU.                          |
| `1`     | Per-core CPU                    | Mostra ogni core CPU separatamente nella sezione alta.         |
| `H`     | Threads                         | Mostra i thread separatamente invece dei soli processi.        |
| `z`     | Color mode                      | Attiva/disattiva colori.                                       |
| `u`     | Filter by user                  | Mostra solo processi di un certo utente.                       |
| `d`     | Change refresh delay            | Cambia ogni quanti secondi `top` aggiorna i dati.              |
| `Space` | Refresh now                     | Forza un aggiornamento immediato.                              |
| `i`     | Idle toggle                     | Nasconde/mostra processi inattivi (`0% CPU`).                  |
| `r`     | Renice                          | Cambia il valore `NI` (nice) di un processo.                   |
| `x`     | Highlight sort column           | Evidenzia la colonna usata per ordinare.                       |
| `y`     | Highlight running tasks         | Evidenzia processi attivi (`running`).                         |
| `e`     | Change memory units (processes) | Cambia unità memoria nella tabella processi.                   |
| `E`     | Change memory units (summary)   | Cambia unità memoria nella sezione alta (`KiB`, `MiB`, `GiB`). |
| `f`     | Fields management               | Aggiunge/rimuove colonne dalla tabella.                        |
| `W`     | Write config                    | Salva la configurazione attuale di `top`.                      |
| `=`     | Reset sort                      | Resetta ordinamenti e filtri.                                  |
| `o`     | Filter fields                   | Filtra processi usando condizioni.                             |
| `L`     | Locate/search again             | Continua la ricerca precedente.                                |
| `h`     | Help                            | Mostra la schermata di aiuto con tutti i comandi.              |
| `A`     | Alternate display mode          | Modalità multi-finestra/advanced.                              |
| `g`     | Choose window                   | Cambia finestra nella modalità avanzata.                       |
| `a`     | Alternate colors                | Cambia gruppi colore/focus.                                    |
| `s`     | Secure delay change             | Simile a `d`, cambia il refresh (dipende dai permessi).        |


---  
[[CPU (Central Processing Unit)]]
[[RAM (Random Access Memory)]]
