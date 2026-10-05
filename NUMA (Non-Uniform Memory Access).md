---
date: 2026-05-27
tags:
  - informatica
  - pubblico

---
# NUMA (Non-Uniform Memory Access)
---
Architettura CPU/RAM usata soprattutto nei server con più di un socket, dove diverse CPU hanno sezioni di RAM più vicine o più lontane tra loro.

In sistemi NUMA:
- ogni CPU/socket ha RAM locale associata
- accedere alla RAM locale è più veloce, accedere alla RAM collegata ad altre CPU è più lento

È da qui che viene il nome, perchè l’accesso alla memoria non ha costo uniforme (non-uniform) lungo tutta la scheda madre.

Gli hypervisor moderni ([[KVM (Kernel-based Virtual Machine)]], VMware etc.) possono esporre la topologia NUMA anche alle VM, il che permette al guest di ottimizzare l'allocazione della memoria e lo scheduling CPU per carichi molto pesanti (database, HPC, AI, grosse VM enterprise).

Per VM piccole/medie su host dal singolo socket, NUMA non serve e aggiunge solo altra complessità.

---
[[QEMU (Quick EMUlator)]]