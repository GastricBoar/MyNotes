---
date: 2026-03-17
tags:
  - informatica
  - pubblico

---
# Directory nei filesystem
---
Una struttura interna ai filesystem, associa i nomi dei file alle loro posizioni sul disco.

Hai visto come un file viene scritto a disco in questa nota sul [[FAT (File Allocation Table)]], e ora ti starai chiedendo "ma come fa il sistema operativo a sapere dove comincia il file?"; 

La risposta è: lo sa perchè il filesystem include questa struttura dedicata chiamata directory, con dentro le directory entry; ciascuna entry contiene nome del file, estensione, metadati e cluster di partenza su disco.

---
[[Cluster (o settori) nei filesystem]]