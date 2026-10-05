---
date: 2026-04-05
tags:
  - informatica
  - pubblico

---
# CoW (Copy-on-Write)
---
Un meccanismo per il quale i dati a disco non vengono mai modificati direttamente: quando devono cambiare, il sistema scrive una copia modificata in un'altra posizione, e aggiorna i riferimenti che il file usa per puntare ai blocchi "grezzi" su disco (i dati stanno sui blocchi, il file è solo la mappa che punta ai blocchi).

I dati originali non vengono sovrascritti, saranno rimossi solo quando non servono più (ricorda, non è detto vengano eliminati immediatamente per il modo in cui funzionano i dischi).

In questo modo, eviti di perder dati in caso di corruzione, blackout, o errori vari.

---
[[Btrfs (B-tree file system)]]
[[ReFS (Resilient File System)]]
[[APFS (Apple File System)]]