---
date: 2025-02-02
tags:
  - informatica
  - pubblico

---
# Internet
---
Una rete globale che collega dispositivi e reti locali lungo tutta la terra, permettendo loro di comunicare.

### La storia
Comincia tra gli anni '50 e '60: America e unione sovietica si trovavano in guerra fredda.

L'unione sovietica sperimentava con le armi nucleari, e gli americani temevano i loro sistemi di comunicazione potessero essere distrutti da un momento all'altro; sai perchè erano così spaventati? perchè le reti telefoniche tradizionali sono affidate a una centrale telefonica, e distruggere quella centrale avrebbe fatto crollare un'intera rete di comunicazioni.

Un singolo punto di fallimento non è una cosa buona in questi casi, quindi si pensò a un sistema di comunicazioni decentralizzato in cui i messaggi trovano da soli il percorso migliore; questo protegge la comunicazione anche in caso vengano distrutti dei nodi. 

Nel 1961 il ricercatore Paul Baran iniziò a sviluppare idee per reti di comunicazioni distribuite, e tra i concetti fondamentali di questo approccio c'era la commutazione di pacchetto (packet switching): suddividi i dati in pacchetti capaci di viaggiare in rete e raggiungere una stessa destinazione anche tramite percorsi differenti.

### La prima rete: ARPANET 
Nel 1958 gli Stati Uniti fondano l'ARPA (Advanced Research Projects Agency), un'agenzia governativa dedicata alla ricerca tecnologica, anche in ambito militare. 

L'ARPA finanzia lo sviluppo di ARPANET (Advanced Research Projects Agency Network), una rete per collegare computer situati in università e centri di ricerca distanti tra loro.

Questa rete utilizza la commutazione di pacchetto e il protocollo NCP (Network Control Program), che permette ai computer in rete di scambiarsi dati; NCP era stato progettato specificatamente per ARPANET e non poteva interconnettere altre reti al di fuori.

ARPANET entra in funzione nel 1969: viene trasmesso il primo messaggio tra un computer dell'UCLA (University of California, Los Angeles) e uno dello Stanford Research Institute; si trattava di una singola parola, "LOGIN", di cui però arrivano solo due lettere, "LO". Il collegamento fu stabilito con successo poco dopo, ed entro la fine dell'anno la rete collegava già quattro nodi.

![Pasted image 20261019161834.png](Utilities/Media/Pasted%20image%2020261019161834.png)


### La nascita di Internet
ARPANET cresce, ma non esiste ancora uno standard per far comunicare reti diverse tra loro: il protocollo NCP era pensato per ARPANET, non poteva interconnettere altro. Nel 1974 Vinton Cerf e Robert Kahn contribuiscono allo sviluppo di TCP/IP, una suite di protocolli progettata proprio per questo.

Nel 1983 ARPANET adotta ufficialmente TCP/IP: viene considerata la nascita di Internet moderno.

### DNS e World Wide Web
Tra il 1983 e il 1991 nascono tante altre cose: DNS, i domini, il primo sito web della storia (http://info.cern.ch/), il World Wide Web e altro.

Da notare che Internet e web non sono la stessa cosa: Internet è l'infrastruttura di rete, il web uno dei servizi che funzionano attraverso di essa.

### La diffusione commerciale di Internet
Negli anni '90 Internet si diffonde rapidamente al di fuori degli ambienti militari e accademici. Nascono i primi ISP, che commercialmente offrono accesso alla rete a privati e aziende. 

---
[[Livelli di rete internet]]
[[WAN (Wide Area Network)]]
[[LAN (Local Area Network)]]
[[Packet switching]]
[[DARPA (Defense Advanced Research Projects Agency)]]
[[ARPANET]]
[[Suite TCP IP]]