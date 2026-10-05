---
date: 2025-04-03
tags:
  - informatica
  - pubblico

---
# TLS (Transport Layer Security)
---
Protocollo di sicurezza progettato per proteggere la comunicazione tra due dispositivi attraverso una rete.

Può essere utilizzato, per esempio, per proteggere la comunicazione tra un browser e un sito web, tra un client di posta e un server email oppure tra due dispositivi che comunicano tramite una [[VPN (Virtual Private Network)]].

### Come funziona?
Crea un canale sicuro tra client e server attraverso il quale i dati vengono trasmessi cifrati.

Funziona così: 

- Client e server negoziano i parametri della connessione tramite il TLS handshake.
  
- Il server presenta un certificato digitale emesso da una CA (Certificate Authority), che permette al client di verificarne l'identità.
  
- Una volta stabilita la connessione sicura, i dati vengono trasmessi attraverso il canale cifrato.

TLS non è limitato al web: può essere utilizzato per proteggere diversi protocolli applicativi, come HTTP, SMTP e IMAP.

### Qual è la differenza con SSL?
TLS è il successore di [[SSL (Secure Sockets Layer)]], ormai obsoleto e non sicuro. Non sono due prodotti diversi, sono due versioni dello stesso prodotto: SSL 1.0 > SSL 2.0 > SSL 3.0 > TLS 1.0 > TLS 1.1 > TLS 1.2 > TLS 1.3.

> Really the name change from SSL to TLS was mostly political. SSL was developed by Netscape, and the name change was mostly to add a bit of distance from Netscape for what was supposed to be a protocol to be used by everyone. Particularly to appease Microsoft.

Le versioni moderne di TLS hanno sostituito SSL e offrono maggiore sicurezza. Non dovresti usare SSL, se non per compatibilità in rarissimi casi. 

---
[[HTTPS (HyperText Transfer Protocol Secure)]]
[[Certificato digitale]]


