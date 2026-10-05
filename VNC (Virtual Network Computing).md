---
date: 2026-08-20
tags:
  - informatica
  - pubblico

---
# VNC (Virtual Network Computing)
---
Sistema di condivisione del desktop grafico, ti consente di controllare un computer da remoto visualizzandone l'interfaccia su un altro dispositivo.

### Come funziona?
È basato sul protocollo RFB (Remote Frame Buffer); a differenza di RDP, VNC non trasmette elementi grafici complessi o comandi di sistema, ma invia direttamente i pixel dello schermo aggiornati dal server al client e trasmette indietro movimenti del mouse e pressioni dei tasti.

Utilizza di default la porta TCP 5900, e si basa su architettura client-server, di cui le due componenti principali sono il VNC Viewer e il VNC Server. Per fare un esempio:

- Vuoi usare un portatile per collegarti in desktop remoto al tuo PC fisso di casa, entrambi sotto la stessa LAN.
  
- Installi VNC server sul PC fisso, è il server perchè è lui che "serve" il suo schermo a te; resta in ascolto sulla porta TCP 5900.
  
- Su portatile installi invece VNC Viewer, perchè è lui il client dal quale richiedi visione e controllo.
  
- Ti colleghi al server remoto, lui invia i pixel del suo schermo, tu invii i comandi di mouse e tastiera a lui.

### Le caratteristiche
Un paio:

- È completamente indipendente dal sistema operativo, funziona indistintamente su Windows, Linux, macOS, Android e iOS.

- A differenza di RDP (che di default disconnette l'utente locale Windows quando ci si collega), VNC ti mostra esattamente quello che sta vedendo la persona seduta davanti al PC remoto.
  
- Trovi diverse varianti tutte diverse per prestazioni, funzioni integrate e licenze: TightVNC, UltraVNC, RealVNC, TigerVNC etc.
  
### Precauzioni
Il protocollo VNC nativo non supporta una crittografia solida del flusso video e dei dati, trasmette spesso il traffico in chiaro o cifra solo la password iniziale. RealVNC a confronto offre crittografia end-to-end nativa.

Inoltre, la porta 5900 è ampiamente scansionata e vulnerabile ad attacchi. Per utilizzarlo in sicurezza su reti esterne è consigliato incapsualre la sessione all'interno di un tunnel SSH o connettersi tramite VPN.

---
[[SSH (Secure Shell)]]
[[RDP (Remote Desktop Protocol)]]