---
date: 2026-08-22
tags:
  - informatica
  - pubblico

---
# HTTPS (HyperText Transfer Protocol Secure)
---
Versione sicura di [[HTTP (HyperText Transfer Protocol)]], utilizzata per trasferire risorse tra client e server proteggendo le comunicazioni tramite crittografia.

### Come funziona?
HTTPS utilizza [[TLS (Transport Layer Security)]] per creare un canale cifrato tra client e server, utilizza di default la porta TCP 443. Funziona così:

- Inserisci `https://www.google.com` nel browser.

- Il browser, che è il client, avvia una connessione HTTPS con il server.

- Client e server eseguono un handshake TLS, durante il quale stabiliscono i parametri della connessione e verificano l'identità del server tramite il suo certificato digitale.

- Una volta stabilita la connessione sicura, le richieste e le risposte HTTP vengono trasmesse attraverso il canale cifrato.

### Le caratteristiche
HTTPS protegge la comunicazione in tre modi:

- Impedisce a terzi di leggere i dati trasmessi.

- Impedisce a terzi di modificare i dati durante la trasmissione senza che la modifica venga rilevata.

- Permette al client di verificare che stia comunicando con il server corretto, tramite il certificato digitale.

Attenzione però, perchè rende sicura solo la comunicazione tra server e client: rimangono eventuali vulnerabilità del server o dell'applicazione.


---