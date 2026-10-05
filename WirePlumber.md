---
date: 2026-09-05
tags:
  - informatica
  - linux
  - pubblico

---
# WirePlumber
---
WirePlumber è un session manager per PipeWire, si occupa di gestire automaticamente dispositivi e connessioni audio/video, decidendo come devono essere configurati e collegati tra loro.

### Come funziona?
Se PipeWire si occupa principalmente trasportare i flussi multimediali ai nodi, è WirePlumber che gestisce le regole secondo cui questi flussi e dispositivi devono essere configurati e collegati. 

Per fare un esempio:

- Hai un video aperto su browser, in riproduzione sugli altoparlanti del PC.
- Colleghi delle cuffie Bluetooth mentre il video è in riproduzione.
- WirePlumber vede che è comparso un nuovo dispositivo.
- Applica le sue regole, e può per esempio decidere "sono state collegate le cuffie, impostiamole come uscita predefinita".
- PipeWire continua a ricevere il flusso audio dal browser, ma lo collega questa volta al dispositivo che WirePlumber ha configurato.

Quindi WirePlumber organizza le connessioni, mentre PipeWire ci fa passare dei flussi dentro quelle connessioni.

---
[[PipeWire]]