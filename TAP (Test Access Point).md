---
date: 2026-09-11
tags:
  - informatica
  - pubblico

---
# TAP (Test Access Point)
---
Un dispositivo che permette di creare una copia del traffico di rete che passa attraverso un certo collegamento, così da poterlo analizzare senza interrompere la comunicazione originale.

### Come funziona?
Un TAP di rete dispone generalmente di quattro porte: due per il collegamento tra i dispositivi della rete e due per inviare le copie del traffico ai dispositivi di monitoraggio.

Tu lo inserisci tra due dispositivi, per esempio tra uno switch e un router; lui raccoglie una copia del traffico che attraversa il collegamento e la invia a un dispositivo di monitoraggio, come un IDS, che può quindi analizzarla.

Il flusso originale non viene interrotto e il TAP introduce una latenza molto bassa. Esistono TAP per reti Ethernet cablate, reti wireless e collegamenti in fibra ottica.

<img src="Utilities/Media/Pasted%20image%2020260911231749.png" alt="Pasted image 20260911231749.png" width="346">

### Tipi di TAP
Esistono due tipi di TAP:

- **Passive TAP:** non richiede alimentazione e si limita ad ascoltare il traffico, utilizzando uno splitter per creare una copia del segnale. Può essere utilizzato sia su collegamenti in rame che in fibra.

- **Active TAP:** richiede alimentazione e ritrasmette i segnali ricevuti. Può essere utile quando è necessario rigenerare o ripulire un segnale sporco/degradato, ma in caso di perdita di alimentazione diventa un punto di guasto della rete.

Quando possibile, i TAP passivi sono generalmente preferibili.

### In che modo è diverso dal port mirroring?
TAP e port mirroring forniscono entrambi una copia del traffico, ma funzionano in modo diverso: il TAP copia il traffico tramite un dispositivo dedicato posto sul collegamento, mentre il port mirroring crea una copia del traffico direttamente sullo switch e la invia a una porta di monitoraggio.

Il TAP è quindi utile quando si vuole avere una copia del traffico indipendente dal comportamento dello switch.

---