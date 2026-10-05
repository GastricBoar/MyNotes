---
date: 2026-10-05-21-59
tags:
  - informatica
  - pubblico
---
# ARP (Address Resolution Protocol)
---
Protocollo utilizzato nelle reti IPv4, serve a scoprire il MAC address associato a un determinato indirizzo IP della rete locale.

### Come funziona?
Immagina di avere un PC e una stampante di rete collegati alla stessa rete locale:

- Il PC vuole inviare un documento alla stampante, quindi tramite un pacchetto IPv4.

- Conosce il suo indirizzo IP (es. 192.168.1.50), ma deve mandare il frame Ethernet e non conosce ancora il suo MAC address.
  
- Invia allora una richiesta ARP, una richiesta che tramite broadcast dice a tutti i dispositivi in rete locale "chi ha l'indirizzo IP 192.168.1.50? mi comunichi il suo MAC address".

- La stampante riceve il messaggio, e invia una risposta ARP comunicando il proprio MAC address.

- Il PC associa quel MAC address all'indirizzo IP della stampante, e lo salva nella propria ARP cache, in modo che non debba più fare quella richiesta ARP fin quando quella cache esiste e non viene aggiornata.

Le richieste ARP non sono limitate ai PC, molti dispositivi di rete possono usare ARP, come server o router.

---
[[MAC address]]
[[Ethernet]]
