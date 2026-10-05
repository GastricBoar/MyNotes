---
date: 2026-04-06
tags:
  - informatica
  - pubblico

---
# Thin provisioning
---
Meccanismo che ti permette di creare volumi più grandi dello spazio che hai realmente a disposizione; per esempio hai due dischi da 50 GB e crei un volume da 800 GB.

I dati occupano spazio fisico solo quando vengono effettivamente scritti, ti permette di aggiungere capacità in un secondo momento; pensa a tutti quei cloud AWS che ti promettono TB di spazio: facendo così non "blocchi" spazio preventivamente, ma consumi solo quello che usi fino a quando non ti servirà davvero.

---
[[Storage Spaces (su Windows)]]