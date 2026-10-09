---
date: 2024-12-02
tags:
  - informatica
  - pubblico

---
# Switch
***
Dispositivo di rete utilizzato per collegare più dispositivi all'interno di una [[LAN (Local Area Network)]].

### A che serve?
Immagina di avere tre computer che devono comunicare tra loro: potresti pensare di collegare ogni computer agli altri con un cavo Ethernet, ma la situazione diventerebbe presto affollata; 3 computer richiedono 3 cavi, ma 10 ne richiedono 45. 

Uno switch risolve questo problema, agendo da snodo centrale della rete locale: colleghi ogni dispositivo allo switch, ed è lui che si occupa di inoltrare i dati tra loro.

In una LAN Ethernet, uno switch o una serie di switch collegati tra loro possono, in teoria, mettere in comunicazione fino a 1024 dispositivi; nella realtà pratica invece, il numero di dispositivi collegati alla singola infrastruttura può essere di molto minore (30? 40?).

### Come funziona?
Uno switch è in grado di memorizzare MAC address, ne ha una tabella piena in cui associa a ogni porta il MAC address del dispositivo collegato. 

Mettiamo tu abbia un paio di computer collegati a uno switch, lo switch deve essere in grado di ricevere i dati, capire a quale dispositivo sono destinati e inoltrarli correttamente. Nel pratico succede questo:
  
- Se un dispositivo ha bisogno di parlare con un altro dispositivo, invia un frame Ethernet allo switch; tra le tante cose, il frame contiene il MAC address del dispositivo di destinazione.

- Lo switch riceve il frame Ethernet, e legge il MAC address del dispositivo di destinazione indicato.
  
- Controlla la propria tabella di MAC address per capire a quale porta è collegato quel dispositivo.
  
- Inoltra il frame verso quella porta.
  
Uno switch non conosce fin dall'inizio i MAC address dei dispositivi collegati alla rete, la sua tabella MAC è inizialmente vuota e la riempie progressivamente in due modi:

- Riceve frame dalle porte e ne associa il MAC address.
  
- Se invece riceve un frame destinato a un MAC address che non ha mai visto prima, inoltra frame sulle porte per scovarlo e associarlo alla porta.

### In che modo è diverso da un hub?
È più "intelligente" di un hub, perchè a differenza sua:

- È in grado di memorizzare il MAC address di ogni dispositivo in LAN. 
- Inoltra frame soltanto verso la porta di destinazione, invece che a tutti i dispositivi indistintamente.

### Tipi di switch
A seconda del livello di controllo e configurazione che offrono all'amministratore di rete:

- **Switch unmanaged:** praticamente Plug and Play, tu colleghi i dispositivi e lui gestisce il traffico; è economico e adatto a reti semplici, ma non ci configuri funzionalità avanzate.

- **Switch managed:** ti permette di configurare lo switch tramite interfaccia di gestione, è più costoso e offre funzionalità utili come VLAN, QoS, monitoraggio e regole di port security.

### Gli switch più utilizzati
A seconda del contesto in cui vengono usati:

- **In ambito aziendale strutturato:** Cisco Catalyst, Aruba CX, Juniper EX Series, Arista 7000 Series.

- **In ambito data center:** Cisco Nexus, Arista EOS Series, Juniper QFX Series.

- **In ambito PMI e Prosumer:** Ubiquiti UniFi, MikroTik CRS, Cisco Business (CBS), Netgear Smart/Plus.

- **In ambito domestico o Plug & Play:** TP-Link TL-SG, Netgear GS, Tenda SG.

***
[[Router]]
[[Ethernet]]
[Testare porte su uno switch utilizzando un loopback plug]([[Loopback plug]])
[[Cavo Ethernet (su rame)]]
[[Patch panel]]
[[Hub]]
[[MAC address]]
[[VLAN (Virtual LAN)]]
[[QoS (Quality of Service)]]