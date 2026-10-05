---
date: 2026-04-05
tags:
  - informatica
  - pubblico

---
# Journaling (in filesystem)
---
Un meccanismo pensato per proteggere la coerenza del filesystem in caso di crash: prima di scrivere blocchi, annota su un journal le operazioni da eseguire. Facendo un esempio:

1. filesystem registra nel journal "seguirò tre step in serie per questa operazione: scrivo dati, aggiorno inode e infine directory"; a serie completata registra un "commit".
2. blackout tra step 2 e step 3.
3. senza journaling potresti ritrovare il filesystem inconsistente.
4. con journaling, il filesystem verifica "quali operazioni son state eseguite? la serie? il commit è stato registrato?"
5. se il commit non è stato registrato, ignora le operazioni precedenti e riporta allo stato coerente.
6. se il commit è stato registrato, le operazioni vengono considerate valide
7. anche a commit registrato, può capitare manchi qualche blocco da scrivere, in quel caso non è un problema farlo per il filesystem.

---
