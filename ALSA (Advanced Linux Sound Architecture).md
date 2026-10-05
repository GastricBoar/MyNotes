---
date: 2026-09-05
tags:
  - informatica
  - linux
  - pubblico

---
# ALSA (Advanced Linux Sound Architecture)
---
Sistema audio del kernel Linux, fornisce ai programmi e ai server audio un'interfaccia standard per comunicare con l'hardware audio.

### Come funziona?
I server audio (es. PipeWire) non comunicano in maniera autonoma con l'hardware audio, ma si appoggiano al supporto fornito dal kernel tramite ALSA.

La tua scheda audio deve poter essere utilizzata dal sistema operativo, e ALSA ci lavora a basso livello tramite il kernel, fornendo al sistema operativo un modo per comunicare con questi dispositivi. Il giro è questo:

- ALSA espone i dispositivi audio al sistema attraverso delle interfacce, chiamate dispositivi ALSA. Per esempio potrebbe rendere disponibile una scheda audio con i suoi ingressi e uscite.
  
- PipeWire può poi utilizzare queste interfacce per accedere all'hardware e gestire i flussi audio.

### PipeWire e WirePlumber
La differenza è il livello a cui operano:

- ALSA fornisce l'accesso a basso livello all'hardware audio tramite il kernel.
  
- PipeWire gestisce i flussi audio e le connessioni tra applicazioni e dispositivi.
  
- WirePlumber stabilisce le regole secondo cui PipeWire configura e collega questi dispositivi e flussi.

---
[[Linux]]
[[Kernel]]
[[PipeWire]]
[[WirePlumber]]