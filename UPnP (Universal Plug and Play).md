---
date: 2026-08-04
tags:
  - informatica
  - pubblico

---
# UPnP (Universal Plug and Play)
---
Un insieme di protocolli di rete, permette ai dispositivi che risiedono sulla stessa LAN di scoprirsi e configurare alcuni servizi senza intervento manuale.

### Come funziona?
Uno degli utilizzi più comuni di UPnP è il port forwarding automatico: un'applicazione può chiedere al router di aprire temporaneamente una porta verso il proprio dispositivo, senza che tu debba accedere al pannello di configurazione del router.

Per fare un esempio:

- Installi un server di gioco sul tuo PC.
- Il server deve essere raggiungibile da Internet sulla porta 25565.
- All'avvio, il programma invia una richiesta UPnP al router.
- Il router crea automaticamente una regola di port forwarding che inoltra la porta 25565 verso il tuo PC.
- Quando il server viene chiuso, la regola può essere rimossa automaticamente.

UPnP è molto comodo in ambito domestico. Tuttavia, se un dispositivo della rete viene compromesso da malware, potrebbe sfruttare UPnP per aprire porte verso Internet. Per questo motivo è spesso consigliato disabilitarlo quando non è necessario o in reti dove si preferisce avere un controllo esplicito sulle regole di inoltro delle porte.

### In che modo è diverso da LLDP?
Entrambi permettono ai dispositivi di annunciarsi all'interno di una rete, ma lo fanno a livelli e per scopi completamente diversi.

UPnP serve a individuare servizi ed applicazioni sulla rete locale e a configurarli automaticamente. Ad esempio, una Smart TV che trova un server multimediale sul NAS o una console che chiede al router di aprire una porta; risponde alla domanda "Che servizi offri e come posso usarli?".

LLDP, invece, descrive la topologia fisica dell'infrastruttura di rete (a Livello 2). Serve a switch, router e apparati di rete per capire quali cavi sono collegati a quali porte; risponde alla domanda "Chi sei e a quale porta fisica sono connesso?".


---