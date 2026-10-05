---
date: 2026-04-06
tags:
  - informatica
  - pubblico

---
# Storage Spaces (su Windows)
---
Tecnologia Windows che ti permette di fare [[RAID (Redundant Array of Independent Disks)]] a livello software, è un moderno successore al RAID software da pannello disk management di Windows.

A differenza di quel vecchio approccio, è più flessibile e sicuro. Funziona così:

1. crei un pool di dischi
2. selezioni il tipo di volume da creare sopra il pool
3. "simple" è un equivalente RAID 0
4. "two way mirror" è un equivalente RAID 1/10
5. "parity" è un equivalente RAID 5
6. "three way mirror" è una sorta di software RAID proprietario Microsoft, richiede almeno 5 dischi per funzionare; ha dei vantaggi tipo il poter utilizzare dischi di dimensione diversa senza sacrificare capacità, e ti garantisce una tolleranza al guasto di 2 dischi senza perdita dati

Storage Spaces ti permette di fare [[Thin provisioning]].

---
