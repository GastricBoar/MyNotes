---
date: 2026-10-20-21-23
tags:
  - informatica
  - pubblico
---
# Modello TCP/IP
---
Rappresentazione concettuale che descrive come avviene la comunicazione tra dispositivi attraverso una rete.

### Il contesto
I dispositivi comunicano attraverso le reti, e succedono tante cose quando i dati si muovono da un posto a un altro: bisogna identificare le applicazioni coinvolte, preparare i dati, individuare la destinazione, trasferire le informazioni attraverso i collegamenti di rete etc.

È un processo complesso che richiede tecnologie e protocolli diversi, sai cosa potrebbe aiutare a capire il suo funzionamento e il modo in cui tutte le parti interagiscono tra loro? una rappresentazione.

Il modello TCP/IP è una di queste rappresentazioni. Non è che sia l'unica rappresentazione possibile, ce ne sono altre, per esempio il modello OSI. Questo è il mio modello TCP/IP. Ce ne sono tanti come lui, ma questo è il mio. Senza di me, il mio modello TCP/IP non è niente. Senza il mio modello TCP/IP, io sono niente.

### Come funziona?
Suddivide il processo di comunicazione in quattro livelli, ogni livello raggruppa funzioni specifiche e utilizza i servizi del livello sottostante per svolgere il proprio compito.

Ecco i quattro livelli, e tieni a mente questo esempio: usi il tuo browser per guardare un video su Youtube.

#### Applicazione
Definisce le regole e il formato dei messaggi che le applicazioni seguono per comunicare attraverso la rete:

- Apri YouTube e scegli un video. 
- Il browser usa HTTP, richiede al server di Youtube le risorse necessarie alla riproduzione del video.
- DNS traduce il nome del server nel suo indirizzo IP.

Come vedi, definisce solo le regole con il quale il browser richiede e riceve risorse; non si occupa di trasportare i dati attraverso la rete.

#### Trasporto
Gestisce il trasferimento dei dati tra le applicazioni:

- Il server di YouTube deve inviare al tuo PC i dati necessari a riprodurre il video.

- La connessione utilizza un certo protocollo di trasporto, cambia in base a come i dati devono essere trasferiti, es. TCP offre ordine e affidabilità nella consegna dei dati, UDP non fornisce garanzie.

- Il protocollo di trasporto usa i numeri di porta per distinguere le comunicazioni e consegnare i dati all'applicazione corretta.


---