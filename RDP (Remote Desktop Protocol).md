---
date: 2026-08-20
tags:
  - informatica
  - pubblico

---
# RDP (Remote Desktop Protocol)
---
Protocollo di rete proprietario sviluppato da Microsoft, consente a un utente di connettersi e controllare un altro computer da remoto tramite interfaccia grafica

### Come funziona?
Su Windows si avvia tramite applicazione integrata o tramite comando `mstsc`. Le versioni Home di Windows non supportano RDP, quindi ti serve una versione Pro o Enterprise o altro.

Utilizza di default la porta TCP/UDP 3389.

### Le caratteristiche
Tutto il traffico trasmesso tra client e server (e sono inclusi i movimenti del mouse, le pressioni dei tasti e il flusso video) viene cifrato utilizzando il protocollo TLS/SSL.

### Precauzioni
La porta 3389 è bersaglio frequente di attacchi brute-force, in ambito aziendale non esporla mai direttamente su Internet, proteggila posizionando la connessione dietro una VPN o un gateway RDP.

---
[[VNC (Virtual Network Computing)]]