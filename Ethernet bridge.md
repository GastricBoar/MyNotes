---
date: 2026-11-10-18-15
tags:
  - informatica
  - pubblico
---
# Ethernet bridge
---
Un bridge è una funzione di rete che collega due o più interfacce Ethernet, permettendo loro di comunicare all'interno dello stesso dominio layer 2.

### Come funziona?
Opera al layer 2 del modello OSI (quindi il data link layer), e funziona così:

- Collega più interfacce Ethernet in un unico segmento layer 2.
- Apprende gli indirizzi MAC dei dispositivi collegati, e le interfacce attraverso cui sono raggiungibili.
- Segna questi dati in una tabella interna chiamata MAC address table, detta anche Forwarding Database (FDB) o Bridge table.

La MAC address table non è da confondere con la ARP table: quella associa indirizzi IP a indirizzi MAC, questa associa indirizzi MAC a porte, che siano esse virtuali (come le interfacce di rete virtuali di un bridge software) oppure fisiche (le porte fisiche di uno switch).

Nel pratico, un bridge lo configuri da CLI, da interfacce software (es. RouterOS) e simili.

Per fare due esempi:

- In RouterOS puoi creare un bridge e inserirci più interfacce fisiche di uno switch Microtik.
- In Linux useresti `sudo ip link add br0 type bridge` per creare il bridge virtuale, e poi altri comandi per aggiungerci le interfacce virtuali.

In entrambi i casi hai lo stesso risultato: le interfacce del bridge appartengono allo stesso dominio layer 2, e il bridge gli permette di scambiarsi frame Ethernet.

---
[[Frame]]
[[Switch]]
