---
date: 2026-09-05
tags:
  - informatica
  - pubblico

---
# ROCm (Radeon Open Compute)
---
Piattaforma software open source sviluppata da AMD, permette di utilizzare GPU AMD per il calcolo parallelo, fornendo strumenti, librerie e runtime necessari per eseguire applicazioni di calcolo e AI su GPU.

### Il contesto
Una GPU non viene utilizzata solamente per elaborare la grafica: può eseguire anche grandi quantità di calcoli in parallelo, cosa particolarmente utile per machine learning, AI, simulazioni scientifiche e calcolo ad alte prestazioni.

Il problema è che le applicazioni devono poter comunicare con la GPU attraverso un ambiente software appropriato; NVIDIA ha, per esempio, CUDA; AMD offre invece ROCm.

### Come funziona?
ROCm fornisce tutto lo stack software necessario per far comunicare le applicazioni con la GPU AMD, e lo installi quando vuoi utilizzare la tua GPU AMD per calcolo, AI, machine learning e così via. ROCm si appoggia al driver GPU già presenta a sistema, non è installato di default, lo installi come fai per altri pacchetti esterni.

---