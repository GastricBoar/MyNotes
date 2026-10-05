---
date: 2026-05-12
tags:
  - informatica
  - linux
  - pubblico

---
# df (disk free)
---
Comando [[Linux]] utilizzato per verificare spazio totale, utilizzato e libero dei [[Filesystem]] montati sul sistema.

A differenza di [[du (disk usage)]], df non mostra quanto pesa uno specifico file o directory, ma quanto spazio rimane disponibile sul disco o partizione.

### df -h
Mostra informazioni sui filesystem montati: spazio totale, usato, libero, percentuale, e punto di mount.

```
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p2  932G  234G  651G  27% /
```

`h` sta per "human readable".

Lanci il comando con la sintassi `df -h` oppure `df -h [dispositivo]`, es. `df -h dev/sdb1`

---
[[Mount points in Linux]]