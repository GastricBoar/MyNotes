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

- In RouterOS puoi creare un bridge e inserirci più interfacce fisiche di uno switch Mikrotik.
- In Linux useresti `sudo ip link add br0 type bridge` per creare il bridge virtuale, e poi altri comandi per aggiungerci le interfacce virtuali.

In entrambi i casi hai lo stesso risultato: le interfacce del bridge appartengono allo stesso dominio layer 2, e il bridge gli permette di scambiarsi frame Ethernet.

### Bridge a layer 3
Un bridge può essere utilizzato anche come interfaccia layer 3, alla quale assegnare un indirizzo IP.

Per esempio, con un router Mikrotik:

- Hai quattro porte: `ether2`, `ether3`, `ether4`,  `ether5`.
- Ogni porta ha la propria interfaccia di rete.
- Se assegni l'indirizzo `192.168.88.1/24` a `ether2`, potresti collegare il PC e raggiungere il Mikrotik attraverso quella porta.
- Se sposti il PC sulla `ether3` non lo raggiungi, perchè non fa parte di quella rete. 
- Allora crei un bridge layer 3, è un'interfaccia logica che raggruppa le interfacce fisiche che ci metti dentro, es. dalla 2 alla 5.
- Assegni al bridge l'indirizzo `192.168.88.1/24`.
- Adesso raggiungi il Mikrotik se colleghi il PC su una qualsiasi delle porte che fanno parte del bridge.

Attenzione che l'indirizzo IP npn viene assegnato a tutte le interfacce fisiche che fanno parte del bridge: viene assegnato all'interfaccia logica del bridge stesso.

Le porte fisiche continuano a trasportare frame Ethernet, mentre il bridge costituisce il punto di accesso layer 3 del router per tutte le porte che ne fanno parte. In questo modo il router può utilizzare un unico indirizzo IP per comunicare con i dispositivi della LAN, senza dover assegnare un indirizzo IP separato a ciascuna porta fisica.

---
[[Frame]]
[[Switch]]
