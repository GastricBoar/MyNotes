---
date: 2026-10-21-23-00
tags:
  - informatica
  - pubblico
---
# Porte di rete
---
Identificatori numerici utilizzati dai protocolli di trasporto, permettono al sistema operativo di distinguere le comunicazioni e consegnare dati al programma corretto.

### Come funziona?
Il tuo PC ha a che fare con tanti programmi diversi che comunicano attraverso la rete contemporaneamente: il tuo browser carica un video su YouTube, Discord riceve messaggi, Steam scarica un aggiornamento e così via. 

Sappiamo che un'indirizzo IP identifica un dispositivo all'interno della rete, ma poi com'è che il tuo PC distingue i dati destinati a tutte queste diverse applicazioni? lo fa con le porte:

- Quando guardi un video su YouTube, il tuo browser comunica con il server di YouTube che ospita quel video.
  
- Il server riceve la richiesta sulla porta 443 (di HTTPS).
  
- Invia la risposta al tuo PC tramite i protocolli di trasporto (es. TCP e UDP), sempre attraverso la stessa connessione su porta 443.
  
- Il tuo PC deve ricevere quei dati.
  
- Associa la comunicazione a una porta locale temporanea, es. la 53124.
  
- Riceve i dati, tu guardi il video su Youtube.

- Se nello stesso momento Discord o Steam stanno ricevendo dati, useranno un'altra porta temporanea.

---
[[Modello TCP IP]]
[[TCP (Transmission Control Protocol)]]
[[UDP (User Datagram Protocol)]]
[[HTTPS (HyperText Transfer Protocol Secure)]]