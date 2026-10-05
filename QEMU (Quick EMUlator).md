---
date: 2026-05-25
tags:
  - linux
  - informatica
  - pubblico

---
# QEMU (Quick EMUlator)
---
Software che emula e gestisce hardware virtuale per macchine virtuali.

Si occupa di emulare cose come: scheda madre, BIOS/UEFI, dischi, controller per storage, schede di rete, periferiche, bus PCI etc.

### Come funziona?
Il contesto è:

- le CPU hanno un loro linguaggio, CPU diverse parlano diversi linguaggi (x86,64, ARM, PowerPC etc.) in base a produttore, generazione o perfino modello all'interno della stessa serie
  
- una VM esegue istruzioni CPU, come qualsiasi altra macchina
  
- se host e guest parlano in architetture diverse, è QEMU che si occupa di tradurre questo scambio di informazioni; è un processo molto lento.

### QEMU con KVM
QEMU costruisce il "telaio" della macchina virtuale, ma se host e guest parlano entrambi in x86_64, allora KVM ti permette di accellerare la virtualizzazione della macchina eseguendone gran parte delle istruzioni direttamente su CPU dell'host; è di molto più veloce rispetto alla sola emulazione, che è lenta.

---
[[KVM (Kernel-based Virtual Machine)]]
