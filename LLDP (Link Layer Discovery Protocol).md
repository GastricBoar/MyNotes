---
date: 2026-08-04
tags:
  - informatica
  - pubblico

---
# LLDP (Link Layer Discovery Protocol)
---
Un protocollo di rete utilizzato da dispositivi di rete (switch, router, IP phone e AP Wi-Fi) per scambiare informazioni sulla propria identità e configurazione con dispositivi vicini. È uno standard IEEE (802.1AB)

È un protocollo vendor-neutral, nato per sostituire i protocolli proprietari dei singoli produttori (come il CDP di Cisco).

### Come funziona?
I dispositivi che supportano LLDP inviano periodicamente (in genere ogni 30 secondi) un messaggio ai dispositivi in LAN; contiene una serie di informazioni, come:

- Nome del dispositivo (es. l'hostname che ci assegni)
- Modello e produttore
- Tipo di dispositivo (switch, router, access point, telefono IP, ecc.)
- Capacità supportate
- Indirizzo IP di gestione (se presente)

Per dirne una, lo switch `SW-Piano2` potrebbe inviare un messaggio equivalente a "Mi chiamo SW-Piano2, sono uno switch Cisco e il mio indirizzo di gestione è 192.168.1.2."

Il dispositivo collegato riceve queste informazioni, può mostrarle a te o utilizzarle per funzionalità automatiche, come la configurazione automatica di telefoni IP o access point:

- Colleghi un nuovo telefono IP a una presa di rete in ufficio.
- Il telefono non sa a quale porta dello switch è collegato né su quale VLAN debba configurarsi.
- Appena si accende, il telefono invia e riceve pacchetti LLDP con lo switch di piano.
- Lo switch gli risponde via LLDP: "Sei sulla porta 12 dello switch 3, posizionati sulla VLAN 20 per la voce e usa 15.4W di alimentazione PoE".

LLDP non attraversa i router: i messaggi vengono scambiati tra dispositivi direttamente collegati sulla stessa rete, di livello 2 quindi.

### In che modo è diverso da UPnP?
Entrambi permettono ai dispositivi di presentarsi tra loro, ma lo fanno con modalità e scopi diversi.

LLDP descrive l'infrastruttura di rete, lo scopo è aiutare te e altri dispositivi a identificare correttamente ciò a cui sono collegati; risponde alla domanda "Chi sei?"

UPnP, invece, serve a individuare dispositivi e servizi disponibili sulla rete locale e a configurarli automaticamente. Ad esempio, un server di gioco può chiedere al router di aprire una porta tramite UPnP, oppure una Smart TV può trovare automaticamente un server multimediale sul tuo NAS; risponde alla domanda "che servizi offri e come posso usarli?".

---
[[Router]]
[[IEEE (Institute of Electrical and Electronics Engineers)]]
[[UPnP (Universal Plug and Play)]]