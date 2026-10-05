---
date: 2026-08-17
tags:
  - informatica
  - pubblico

---
# SAN (Storage Area Network)
---
Una rete che fornisce a uno o più server accesso diretto a uno storage remoto, facendolo apparire come un disco locale.

### Come funziona?
Facendo un esempio:

- Hai un server, o più di un server.
- Il disco locale non lo vuoi utilizzare, ma ne vuoi uno remoto.
- Da qualche altra parte hai uno storage, altro non è che un computer con CPU, RAM, disco e porta di rete.
- Colleghi server e quello storage tramite cavo iSCSI, che ti permette di trasportare su rete Ethernet le stesse operazioni che faresti su un disco locale.
- Il tuo server vede il disco remoto come un disco locale, per esempio `/dev/sdb`.
- Puoi utilizzarlo proprio come fosse un disco locale.

Una SAN fornisce accesso a livello di blocco, e quando dico "a livello di blocco" intendo che il server può chiedere allo storage "scrivi o leggi questi dati tra i blocchi 1500 e 1600", e può costruirci sopra un filesystem; interagisce con lo storage come un disco grezzo, non come un insieme di file e cartelle.

### Che differenza fa con un NAS?
La differenza è nel modo in cui i dati vengono presentati al server:

- In una SAN il dispositivo viene presentato al server a livello di blocco: il server dice "dammi un disco", vede un disco, ed è lui stesso che gestisce disco e filesytem.
  
- Al NAS un server direbbe "dammi file o cartelle", per esempio come `\mnt\foto`, ma rimane il NAS a gestire disco e filesystem.

---
[[iSCSI (Internet SCSI)]]
