---
date: 2026-11-10-21-36
tags:
  - informatica
  - pubblico
---
# Neighbor table
---
Una tabella che memorizza le associazioni tra indirizzi IP e MAC address dei dispositivi vicini.

### Come funziona?
Un PC che comunica con un dispositivo nella propria subnet ha bisogno di conoscere il suo indirizzo MAC; la neighbor table gestisce queste informazioni, e funziona così:

- La tabella contiene le associazioni tra indirizzi IP e MAC address, ma non è lei che li raccoglie in primo luogo.
- I protocolli ARP (per l'IPv4) e NDP (per l'IPv6) risolvono gli indirizzi IP in MAC address.
- La tabella ne conserva i risultati.

È una struttura comune a tanti sistemi operativi diversi.

---