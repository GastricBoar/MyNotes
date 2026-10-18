---
date: 2024-12-30
tags:
  - informatica
  - pubblico

---
# TCP (Transmission Control Protocol)
***
Un protocollo di rete utilizzato per trasmettere dati in modo "affidabile" tra applicazioni, garantisce arrivino correttamente e nell'ordine previsto. 

### La storia
Nel 1974, Vinton Cerf e Robert Kahn proposero un sistema chiamato Transmission Control Program (TCP); era progettato per consentire a reti diverse di comunicare, e si occupava sia di trasportare dati che di instradare le reti.

Nel 1978 venne suddiviso in due protocolli distinti:
- **IP (Internet Protocol)**: indirizza e inoltra i pacchetti tra reti.
- **TCP (Transmission Control Protocol)**: trasporta in maniera affidabile dati.

Da quel momento, TCP e IP sono diventati due componenti fondamentali della suite TCP/IP.
### Come funziona?
Garantisce una comunicazione affidabile tra applicazioni; la chiamo "affidabile" perchè si assicura che i dati inviati dal mittente arrivino al destinatario in maniera corretta, anche in presenza di problemi di rete.

Nel pratico funziona così:

- Il client chiede al server di stabilire una connessione, dicendo "ci sei?"; questo passaggio prende il nome di SYN (Synchronize).

- Il server risponde "ci sono, possiamo comunicare?"; questo passaggio prende il nome di SYN-ACK (Synchronize-Acknowledge)**.

- Il client conferma "sì, iniziamo"; questo passaggio prende il nome di ACK (Acknowledgment)**.

Si chiama three-way handshake.

***
[[UDP (User Datagram Protocol)]]
[[ICMP (Internet Control Message Protocol)]]
[[Protocollo]]
