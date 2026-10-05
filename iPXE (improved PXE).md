---
date: 2026-04-16
tags:
  - informatica
  - pubblico

---
# iPXE (improved PXE)
---
Un'implementazione open source di [[PXE (Preboot Execution Environment)]], che ne estende funzionalità e flessibilità.

### Ma che cambia?
Un paio di cose.

### Download delle immagini tramite HTTP
PXE utilizzava TFTP per scaricare [[Immagine ISO]] da server, iPXE utilizza HTTP che a confronto è più veloce e stabile.

### Script di boot
PXE scaricava e installava, stop; qui invece puoi creare script di boot che concatenano azioni, es. "prendo ip, installo, e avvio sistema".

### Automazioni logiche
Potresti prevedere scenari in cui "se macchina Windows, allora scarica questo; se macchina Linux, scarica quest'altro".

### Supporto al provisioning cloud
Tramite [[API (Application Programming Interface)]] potresti connettere il dispositivo a un server in cloud e reperire i file necessari direttamente da lì.

---
[[ZTI (Zero Touch Installation)]]