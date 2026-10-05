---
date: 2025-01-08
tags:
  - informatica
  - pubblico

---
# nslookup (Name Server Lookup)
***
Strumento da riga di comando, viene usato per interrogare un server [[DNS (Domain Name Server)]] e ottenere diverse informazioni.
###### **Verificare un server DNS sia funzionante**
Tramite nslookup fai delle query a diversi domini, ma puoi anche specificare il server DNS dal quale vuoi passino queste query. Se il server DNS che hai indicato manda in timeout qualsiasi richiesta fatta, allora puoi capire che non funziona, alzare la cornetta del telefono e dire a qualcun altro "oh vedi che il server DNS è giù".

Ecco come fare:

1. Invia un `nslookup` per avviare la modalità interattiva. Di default, le query vengono fatte passare dal server DNS attualmente in uso.

2. Invia il comando `server [IP server]` per definire il server DNS dal quale vuoi far passare la query, per esempio `server 8.8.8.8`.

3. Fa' una query a un dominio, per esempio invia `www.google.com`.

4. Se il server DNS funziona correttamente, riceverai una risposta del genere:

5. Se il server DNS non funziona, riceverai un timeout:

***
[[tracert (traceroute)]]

[[Record DNS]]

[[ipconfig]]