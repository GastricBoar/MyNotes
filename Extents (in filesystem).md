---
date: 2026-04-05
tags:
  - informatica
  - pubblico

---
# Extents (in filesystem)
---
Un meccanismo che ti permette di indicare una serie di blocchi contigui con una sola informazione.

In un filesystem [[FAT (File Allocation Table)]] i blocchi per file vengono indicati singolarmente (es. blocco 100, blocco 101, blocco 102, blocco 103 etc.) mentre in ext4 gli extents ti permettono di indicare più blocchi in una volta sola con un solo record "da blocco 100 a blocco 103".

Fare questo riduce di molto la quantità di metadati da leggere e gestire, perchè se prima servivano 250.000 righe a descrivere un file che occupa 250.000 blocchi, adesso bastano poche righe di extents per fare la stessa cosa; è un accesso più efficiente, meno operazioni di I/O sui metadati.

---
[[ext4 (fourth extended filesystem)]]