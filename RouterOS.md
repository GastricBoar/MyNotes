---
date: 2026-11-10-20-04
tags:
  - informatica
  - pubblico
---
# RouterOS
---
Il sistema operativo sviluppato da MikroTik per i propri dispositivi di rete. Ti permette di gestire infrastrutture di rete tramite routing, switching, firewalling, wireless networking, VPN e monitoraggio.

### Come funziona?
È un sistema operativo proprietario, basato su kernel Linux modificato, ma con proprie shell, pacchetti e comandi.

RouterOS organizza i comandi in una struttura ad albero, ogni ramo rappresenta un'area funzionale, così:

- `/interface`: ethernet, wifi, bridge
- `/ip`: address, dhcp-client, dhcp-server, dns, firewall, route
- `/system`: identity, package, resource, users
- `/tool`: ping, traceroute

I comandi non invocano necessariamente un programma indipendente come in Linux: spesso stai interrogando direttamente un componente della configurazione dell'apparato di rete.

Un comando esempio è `/ip address print`, e lo leggi così:

- `/`: parti dalla radice.
- `ip`: entra nell'area relativa alla configurazione IP.
- `address`: seleziona la gestione degli indirizzi IP.
- `print`: visualizza gli elementi configurati.

### Spostarsi tra aree funzionali
Se scrivi `/ip` il terminale ti diventa `[admin@hAP] /ip>`, e da lì puoi eseguire direttamente `address print`. Puoi spostarti tra aree digitando `/{nome-area}`, per esempio `/interface`, `/ip`, `/system` e così via.

### Manuali e aiuto
Se hai bisogno di visualizzare i completamenti disponibili per una certa area, digiti `/{nome-area}` e premi Tab:

```
[admin@hAP] /ip> address 
  
add     comment     disable     edit     enable     export     find     print    

```


---