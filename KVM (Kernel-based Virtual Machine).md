---
date: 2026-05-24
tags:
  - informatica
  - linux
  - pubblico

---
# KVM (Kernel-based Virtual Machine)
---
Modulo del [[Kernel]] [[Linux]], che ti permette di accellerare la virtualizzazione di macchine basate su architettura x86_64.

### In che senso "accellerare"?
Qui serve fare una digressione per contesto:

- le CPU hanno un loro linguaggio, e CPU diverse parlano diversi linguaggi (x86,64, ARM, PowerPC etc.) in base a produttore, generazione o perfino modello all'interno della stessa serie
  
- una VM esegue istruzioni CPU, come qualsiasi altra macchina
  
- se host e guest parlano in architetture diverse, all'hypervisor tocca tradurre ed emulare continuamente queste istruzioni (emulazione); è molto lento
  
- anche virtualizzare guest x86_64 su host x86_64 era difficile in passato, perchè le CPU non erano progettate per distinguere tra host e guest virtualizzati

- prima di KVM, l'hypervisor doveva costantemente intercettare le istruzioni ricevute dal guest, per assicurarsi di parare quelle istruzioni sensibili che hanno a che fare con operazioni privilegiate (es. memoria, interrupt, page tables); questo lavoro accumula overhead, ma è necessario perchè istruzioni incaute avrebbero potuto danneggiare l'host

- col tempo, le CPU moderne hanno introdotto estensioni hardware di virtualizzazione (es. AMD-V o Intel VT-x), pensate per distinguere host e guest a livello hardware, e introducendo modalità speciali che permettono al guest di interagire in sicurezza con la CPU
  
- KVM accellera questa comunicazione tra guest e host, perchè quasi tutte le istruzioni inviate dal guest possono essere eseguite direttamente sulla CPU reale, fatta eccezione per alcune operazioni sensibili che vengono temporaneamente passate all'hypervisor
  
- le VM diventano veloci quasi quanto il bare metal

---
[[QEMU (Quick EMUlator)]]
[[libvirt (virtualization library)]]