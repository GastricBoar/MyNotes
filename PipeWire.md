---
date: 2026-09-05
tags:
  - informatica
  - linux
  - pubblico

---
# PipeWire
---
PipeWire è un server multimediale per Linux, gestisce i flussi audio e video tra applicazioni e dispositivi hardware.

### Perchè chiamarlo server?
Perchè in informatica un server non deve essere necessariamente un computer remoto su internet, ma come in questo caso, può essere semplicemente un programma che offre un servizio ad altri programmi, chiamati client.

Per fare un esempio: un player musicale vuole riprodurre una canzone. Non comunica necessariamente direttamente con la scheda audio, ma invia il flusso audio a PipeWire; quindi PipeWire è un programma che offre alle applicazioni un servizio centralizzato per gestire e collegare flussi audio e video.

### Il contesto
Un'applicazione come Tidal, Discord o un browser deve poter inviare audio a una cuffia, a degli altoparlanti. Allo stesso modo, un microfono deve poter inviare il proprio audio a un'applicazione.

PipeWire fa da intermediario, gestendo questi flussi e le connessioni tra le varie sorgenti e destinazioni.

### Come funziona?
In PipeWire ogni applicazione e dispositivo viene rappresentata come un "nodo", e lui gestisce i flussi di dati tra di essi.

Per esempio, quando riproduci un video:

- Il browser genera un flusso audio che viene inviato al nodo PipeWire associato al browser.
  
- PipeWire lo collega poi al sink adatto, ovvero il nodo corrispondente alle cuffie o agli altoparlanti, che ne riproduce il flusso audio.

PipeWire può gestire contemporaneamente molti flussi e collegarli a dispositivi diversi.

### WirePlumber
Se PipeWire si occupa principalmente trasportare i flussi multimediali ai nodi, è WirePlumber che gestisce le regole secondo cui questi flussi e dispositivi devono essere configurati e collegati. 

Per fare un esempio:

- Hai un video aperto su browser, in riproduzione sugli altoparlanti del PC.
- Colleghi delle cuffie Bluetooth mentre il video è in riproduzione.
- WirePlumber vede che è comparso un nuovo dispositivo.
- Applica le sue regole, e può per esempio decidere "sono state collegate le cuffie, impostiamole come uscita predefinita".
- PipeWire continua a ricevere il flusso audio dal browser, ma lo collega questa volta al dispositivo che WirePlumber ha configurato.

Quindi WirePlumber organizza le connessioni, mentre PipeWire ci fa passare dei flussi dentro quelle connessioni.

---
[[WirePlumber]]
