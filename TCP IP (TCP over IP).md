---
date: 2024-12-30
tags:
  - informatica
  - pubblico

---
# TCP/IP (TCP over IP)
***
Suite di protocolli di rete, permette a dispositivi e reti differenti di comunicare tra loro. È alla base della comunicazione su Internet e LAN.

### La storia
Negli anni '70, ARPANET utilizzava NCP (Network Control Program), un protocollo progettato per la comunicazione tra i computer collegati ad ARPANET, che non riusciva però a interconnettere altre reti.

Nel 1974, Vinton Cerf e Robert Kahn proposero quindi il Transmission Control Program (TCP), un sistema progettato per far comunicare reti diverse.

Nel 1978 venne suddiviso in due protocolli distinti:
- **IP (Internet Protocol)**: indirizza e inoltra i pacchetti tra reti.
- **TCP (Transmission Control Protocol)**: trasporta in maniera affidabile dati.

Nel 1983 ARPANET adotta ufficialmente TCP/IP, una tappa fondamentale nella nascita di Internet moderno. I protocolli della suite sono aperti e utilizzabili liberamente, che è perfetto perchè ti permette di non dipendere da un singolo produttore.

Il nome può confondere, perchè il TCP è solo uno dei tanti protocolli di rete usati dalla suite per la comunicazione tra dispositivi; dovremmo rinominarlo "TCP, UDP e ICMP over IP", ma non è una cosa che scivola dalla lingua così facilmente, quindi si è lasciato il nome al protocollo più utilizzato tra tutti.

### Come funziona?
Pensala così: il protocollo TCP mette assieme i pacchetti in un certo modo, mentre il protocollo IP li trasporta su Internet, come fosse un camioncino delle consegne.

***
[[TCP (Transmission Control Protocol)]]
[[UDP (User Datagram Protocol)]]
[[ICMP (Internet Control Message Protocol)]]
[[Internet]]
[[LAN (Local Area Network)]]
