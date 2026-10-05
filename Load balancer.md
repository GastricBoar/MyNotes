---
date: 2026-08-25
tags:
  - informatica
  - pubblico

---
# Load balancer
---
Dispositivo o software che distribuisce le richieste ricevute da un servizio tra più server, permettendo di aumentare disponibilità e capacità del servizio.

Alcuni tra i load balancer hardware sono F5 BIG-IP, Citrix ADC e A10 Thunder ADC, mentre esempi di load balancer software sono HAProxy, NGINX e Apache HTTP Server.

### Come funziona?
Pensa a questo:

- Hai un sito web chiamato `doggos.com` molto affollato.
- Un solo server non è più sufficiente a gestire tutte le richieste.
- Aggiungi altri server che ospitano lo stesso sito.
- Metti un load balancer davanti ai server.
- I client adesso inviano le richieste al load balancer, e lui le distribuisce tra i server disponibili.

### I vantaggi
Utilizzare un load balancer è conveniente per diversi motivi, tra cui:

- **Bilancia il carico:** lo distribuisce tra più server, evitando che uno venga sovraccaricato.
- **Ridondanza:** continui a erogare il servizio anche se uno dei server diventa indisponibile.
- **Flessibilità:** aggiungi o rimuovi server senza modificare il modo in cui i client raggiungono il servizio.

### I metodi di distribuzione
Diversi modi in cui il load balancer decide a quale server inoltrare una richiesta:

- **Round Robin:** distribuisce le richieste a turno tra i server.
- **Least Connections:** invia la richiesta al server che ha meno connessioni attive.
- **IP Hash:** utilizza l'indirizzo IP del client per determinare il server a cui inoltrare la richiesta.

---
[[Proxy]]