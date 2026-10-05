---
date: 2026-09-01
tags:
  - informatica
  - pubblico

---
# Evil Twin
---
Attacco informatico in cui un malintenzionato crea una rete Wi-Fi falsa che imita una rete legittima, con l'obiettivo di convincere gli utenti a connettersi e poter così intercettare o manipolare il loro traffico.

### Come funziona?
L'attaccante crea un access point con SSID di una rete Wi-Fi legittima, cercando di renderlo indistinguibile da quella reale.

Facendo un esempio:

- In un aeroporto esiste la rete Wi-Fi `Airport_Free_WiFi`.
- L'attaccante crea un access point chiamato `Airport_Free_WiFi`, ma potrebbe benissimo avere lo stesso SSID o addirittura lo stesso MAC address.
- Il dispositivo della vittima si connette alla rete dell'attaccante, pensando sia quella legittima.
- L'attaccante intercetta il traffico.

L'Evil Twin è una forma di Man-in-the-Middle, perché l'attaccante si inserisce tra la vittima e Internet.

### Come si previene?
La difesa principale consiste nel verificare che la rete Wi-Fi sia realmente quella legittima e nel proteggere le comunicazioni anche nel caso in cui ci si connetta a una rete non affidabile:

- **Verifica la rete Wi-Fi:** controlla SSID e, quando possibile, chiedi al gestore quale sia la rete ufficiale.
  
- **Usa HTTPS/TLS:** cifra le comunicazioni e permette al dispositivo di verificare l'identità del server.
  
- **Evita reti Wi-Fi aperte:** soprattutto quando devi trasmettere informazioni sensibili.
  
- **Usa una VPN:** crea un canale cifrato tra il dispositivo e il server VPN, rendendo più difficile intercettare il traffico sulla rete locale.
  
- **Disabilita la connessione automatica:** evita che il dispositivo si colleghi automaticamente a reti conosciute senza verificare che siano realmente quelle legittime.

---
[[Man-in-the-Middle (MitM)]]