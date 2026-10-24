---
date: 2026-10-20-21-23
tags:
  - informatica
  - pubblico
---
# Modello TCP/IP
---
Una rappresentazione concettuale, descrive come avviene la comunicazione tra dispositivi attraverso una rete.

### Il contesto
I dispositivi comunicano attraverso le reti, e succedono tante cose quando i dati si muovono da un posto a un altro: bisogna identificare le applicazioni coinvolte, preparare i dati, individuare la destinazione, trasferire le informazioni attraverso i collegamenti di rete etc.

È un processo complesso che richiede tecnologie e protocolli diversi, sai cosa potrebbe aiutare a capire il suo funzionamento e il modo in cui tutte le parti interagiscono tra loro? una rappresentazione.

Il modello TCP/IP è una di queste rappresentazioni. Non è che sia l'unica rappresentazione possibile, ce ne sono altre, per esempio il modello OSI. Questo è il mio modello TCP/IP. Ce ne sono tanti come lui, ma questo è il mio. Senza di me, il mio modello TCP/IP non è niente. Senza il mio modello TCP/IP, io sono niente.

### Come funziona?
Suddivide il processo di comunicazione in quattro livelli, ogni livello raggruppa funzioni specifiche e utilizza i servizi del livello sottostante per svolgere il proprio compito.

Ecco i quattro livelli, e tieni a mente questo esempio: usi il tuo browser per guardare un video su Youtube.

#### Applicazione (Application Layer)
Definisce le regole e il formato dei messaggi che le applicazioni seguono per comunicare attraverso la rete:

- Apri YouTube e scegli un video. 
- Il browser usa HTTP, richiede al server di Youtube le risorse necessarie alla riproduzione del video.
- DNS traduce il nome del server nel suo indirizzo IP.

Come vedi, definisce solo le regole con il quale il browser richiede e riceve risorse; non si occupa di trasportare i dati attraverso la rete.

Esempi di protocolli del livello applicazione sono HTTP e DNS.

#### Trasporto (Transport Layer)
Gestisce il trasferimento dei dati tra le applicazioni:

- Il server di YouTube deve inviare al tuo PC i dati necessari a riprodurre il video.

- La connessione utilizza un certo protocollo di trasporto, cambia in base a come i dati devono essere trasferiti, es. TCP offre ordine e affidabilità nella consegna dei dati, UDP non fornisce garanzie.

- Il protocollo di trasporto usa i numeri di porta per distinguere le comunicazioni e consegnare i dati all'applicazione corretta.

Esempi di protocolli del livello trasporto sono TCP e UDP.

#### Internet (Internet Layer)
"Internet" inteso come "tra reti", non come il grande Internet. Si occupa di ndirizzamento IP e di instradare i pacchetti tra reti diverse:

- I dati che il serve vuole mandare al tuo PC vengono inseriti in pacchetti IP, contengono l'indirizzo IP di mittente e destinatario.

- I pacchetti seguono una catena di router, per ogni hop usano l'indirizzo IP di destinazione per trasferirli alla rete corretta.

Permette ai dati di raggiungere la rete di destinazione, ma non garantisce che i pacchetti arrivino a destinazione. Manca ancora un livello.

Esempi di protocolli del livello Internet sono IP e ICMP.

#### Accesso alla rete (Network Access Layer)
Trasmette i dati attraverso la rete locale: la scheda di rete del tuo PC riceve i frame, tramite Wi-Fi o cavo Ethernet.

Esempi di protocolli e tecnologie del livello di accesso alla rete sono Ethernet e Wi-Fi.\

### E poi?
Da qui il giro riparte verso l'alto: 

- La scheda di rete elabora il frame ed estrae il pacchetto IP.
- Il livello Internet verifica l'indirizzo IP di destinazione.
- Se destinato al tuo PC, passa al livello trasporto, che utilizza le porte per individuare la comunicazione a cui appartengono i dati.
- I dati vengono consegnati al protocollo applicativo corrispondente.
- Li interpreta e li rende disponibili al tuo browser.
- Tu guardi il video.

---
[[Porte di rete]]
[[Hop]]