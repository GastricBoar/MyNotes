---
date: 2026-07-22
tags:
  - informatica
  - pubblico

---
# NetBIOS (Network Basic Input Output System)
---
Interfaccia di programmazione [[API (Application Programming Interface)]] pensata per la gestione dei nomi e delle sessioni all'interno di una rete locale (LAN).

Sviluppata originariamente da Sytek per IBM nel 1981, è stata poi adottata da Microsoft. Non è un vero e proprio protocollo di trasporto di rete, ma ci lavora assieme.

### Il contesto
La comunicazione tra programmi di rete dei PC in LAN era molto diversa negli anni '80: si interfacciavano direttamente tramite i [[MAC address]] delle reciproche schede di rete. Era un problema per diversi motivi: se la scheda di rete viene sostituita devi riconfigurare il programma, gli indirizzi MAC sono difficili da leggere, e ogni produttore di schede di rete ha le proprie librerie e drivers.

NetBIOS è nato per astrarre questa complessità: identifica le macchine tramite nomi intelligibili e apre sessioni di comunicazione senza farti preoccupare dell'hardware di rete sottostante. Con NetBIOS un programma può semplicemente richiedere di connettersi al dispositivo SERVER-DATI, lasciando all'API il compito di trovarlo sulla rete locale.

### Come funziona?
All'interno della rete si occupa di diverse cose:

- **Gestisce nomi:** consente assegnazione e la risoluzione dei nomi NetBIOS, da massimo 15 caratteri.

- **Gestisce sessioni:** permette la connessione orientata alla connessione e affidabile tra due nodi per lo scambio di dati.

- **Gestisce datagrammi:** l'invio di messaggi brevi e senza garanzia di consegna.

NetBIOS da solo non può far viaggiare dati sulla rete fisica, e ha bisogno di un protocollo di rete per farlo. Se ne sono succeduti più di uno:

- **NetBEUI:** il protocollo di trasporto nativo originario, veloce per piccole reti ma non può instradare dati su router o su Internet.

- **NBT (NetBIOS over TCP/IP):** poggia le chiamate NetBIOS sopra pacchetti TCP/IP, il che permette di comunicare attraverso router e su Internet.

### E oggi che si usa?
La maggior parte delle reti Windows non fa più affidamento su NetBIOS: la risoluzione dei nomi passa da DNS, mentre la condivisione di file e stampanti avviene tramite SMB direttamente su TCP, senza NetBIOS. 

Su infrastrutture moderne NetBIOS è spesso disabilitato per sicurezza, o utilizzato solo per retrocompatibilità.

---
[[NetBEUI (NetBIOS Extended User Interface)]]