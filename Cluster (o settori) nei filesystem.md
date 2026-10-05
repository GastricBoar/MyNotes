---
date: 2026-03-15
tags:
  - informatica
  - pubblico

---
# Cluster/settori nei filesystem
---
La più piccola unità di spazio a disco che un [[Filesystem]] può assegnare a un file. Un [dispositivo di archiviazione]([[Dispositivi a blocchi]]) è diviso in blocchi di dimensione fissa, i cluster.

### Quanto sono grandi i cluster? perchè?
Dipende, ma ci son due attori principali nella scelta:

- **Il filesystem:** stabilisce quali sono le dimensioni di cluster possibili; per esempio, FAT32 tipicamente 4/8/16/32KB, ext4 fino a 4KB, NTFS di default 4KB ma può cambiare.
  
- **Il [[Sistema operativo]]:** sceglie il valore in base alla dimensione consigliata, ma puoi anche impostarlo manualmente.

 Facendo un esempio pratico, quando salvi un file da 10 KB:

- se la dimensione del cluster è 4 KB, te ne serviranno tre per un totale di 12 KB
- a questo punto, anche se il file pesa 10 KB e te ne avanzano 2 liberi, il file occuperà comunque tutto lo spazio disponibile.

Come hai visto sono rimasti 2 KB di scarto, e ti starai chiedendo "allora perchè non possiamo fare cluster da 1 KB per evitare scarto?"; la risposta è che così facendo avresti molti più cluster da gestire, con aumento di operazioni in lettura e memoria usata. Qui il gioco consiste nel trovare un buon compromesso tra efficienza dello spazio e overhead di gestione chiesto al filesystem.





---
