---
date: 2026-08-26
tags:
  - informatica
  - pubblico

---
# DoH (DNS over HTTPS)
---
Tecnologia che trasmette le richieste DNS attraverso una connessione HTTPS, proteggendole tramite crittografia.

### Come funziona?
Normalmente una richiesta DNS viene inviata al server DNS tramite protocolli DNS tradizionali, senza crittografia.

Con DoH, invece, la richiesta DNS viene inserita all'interno di una richiesta HTTPS:

- Vuoi raggiungere `https://doggos.com`.
- Il browser deve prima conoscere l'indirizzo IP del server associato a `doggos.com`.
- Invia quindi una richiesta DNS attraverso una connessione HTTPS a un server DNS che supporta DoH.
- Il server DNS risolve il dominio e restituisce l'indirizzo IP.
- La richiesta e la risposta DNS vengono trasmesse cifrate tramite HTTPS.

Fare questo protegge principalmente la confidenzialità della tua richiesta DNS: un osservatore sulla rete non può leggere direttamente quali domini vengono richiesti, diversamente dal DNS tradizionale, dove le richieste potrebbero essere intercettate.

Attenzione perchè non rende anonima la navigazione: il server DNS che riceve la richiesta può comunque sapere quale dominio hai richiesto.

Utilizza normalmente la porta TCP 443, la stessa utilizzata da HTTPS. A confronto DNS tradizionale utilizza la UDP 53.

---
[[DNS (Domain Name Server)]]

[[HTTPS (HyperText Transfer Protocol Secure)]]

[[TLS (Transport Layer Security)]]