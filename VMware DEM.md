---
date: 2024-10-17
tags:
  - informatica
  - pubblico

---
# VMware DEM
---
DEM sta per Dynamic Environment Manager, è uno strumento che [[VMware]] mette a disposizione per centralizzare profili e configurazioni varie di utenti delle macchine virtuali. 

Questi file vengono salvati su una cartella con il nome dell'utente e possono essere posizionati su una cartella condivisa in rete (nel nostro caso, la cartella DEM-Profiles che troviamo in BSHRP01).

VMware salverà nel tempo i dati di ciascuna sessione dell'utente su questa cartella, e li ripristinerà a ogni avvio.

---