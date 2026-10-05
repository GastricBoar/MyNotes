---
date: 2026-09-19
tags:
  - informatica
  - pubblico

---
# GRUB (GRand Unified Bootloader)
---
Bootloader utilizzato principalmente nei sistemi Linux per caricare il sistema operativo durante l'avvio del computer.

### Come funziona?
Quando accendi il computer, il firmware [[UEFI]] o BIOS inizializza l'hardware e avvia il bootloader:

- Il firmware individua il dispositivo fisico da cui effettuare il boot e avvia GRUB.
- GRUB mostra un menù dal quale  scegliere quale sistema operativo o kernel avviare.
- Carica il kernel Linux e eventuali parametri necessari in memoria.
- Trasferisce il controllo al kernel, che conclude l'avvio del sistema operativo.

Useresti GRUB su un PC con sopra Linux e Windows, oppure con sopra diverse versioni del kernel Linux.

---