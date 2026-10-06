---
date: 2025-02-19
tags:
  - informatica
  - pubblico

---
# Firewall
---
Componente software o hardware che monitora il traffico di rete e lo filtra secondo delle regole di sicurezza, lasciando passare solo il traffico sicuro.

### Come funziona?
Immagina di avere una rete collegata a Internet. I dispositivi della rete devono poter comunicare con l'esterno, ma non vuoi che qualsiasi connessione proveniente da Internet possa raggiungere liberamente i tuoi sistemi.

Il firewall controlla il traffico che passa tra la rete interna e l'esterno, e per ogni comunicazione, verifica le informazioni del traffico confrontandole con le proprie regole, es. hai una regola che permette ai client di raggiungere un server sulla porta 443 ma impedisce invece connessioni non autorizzate verso altre porte.

### Firewall stateful
Un firewall analizza i pacchetti in entrata e in uscita e li filtra, ma non tutti i firewall sono uguali; qui bisogna fare delle differenze e introdurre il concetto di "state": un record del traffico che passa o che è passato attraverso la rete. 

Uno state (o tabella di stato) assomiglia a una grossa tabella costantemente aggiornata e monitorata, un quadro di tutto ciò che succede.

Un firewall stateful non analizza il traffico come semplice "insieme di singoli pacchetti", ma ne considera il contesto e il flusso nella sua interezza: analizza i pacchetti a fondo, identifica possibili correlazioni tra loro, o con lo state passato.

Utilizza molte risorse e può introdurre una certa latenza all'interno della rete, è per questo adatto a contesti più grossi.

### Firewall stateless
Non utilizza una tabella di stato, ma una tabella di regole definite dall'amministratore di sistema. Sono cose tipo "blocca tutto il traffico in entrata dalla porta 22" oppure "tieni aperta la porta 21114".

È meno sicuro per grandi contesti, ma è più leggero e conveniente da utilizzare nei piccoli contesti che non hanno bisogno di sicurezza spericolata. Ne sai ancora poco, a suo tempo informati cazzone.

### Firewall host-based e network-based
I firewall possono essere distinti anche in base a dove vengono installati e quale traffico controllano:

- **I firewall host-based** controllano il traffico in entrata e in uscita da un singolo host, si tratta di firewall software installati direttamente su dispositivo. 

- **I firewall network-based** controllano il traffico in entrata e in uscita da un'intera rete, può essere hardware o software; è più complesso da configurare, ma ti offre un controllo globale.

### I firewall più utilizzati
A seconda del contesto in cui vengono usati:

- **In ambito enterprise:** Palo Alto Networks, Fortinet FortiGate, Check Point Quantum, Cisco Secure Firewall.
  
- **In ambito data center:** Palo Alto Networks, Fortinet FortiGate, Cisco Secure Firewall, Check Point Quantum.
  
- **In ambito PMI e Prosumer:** Fortinet FortiGate, Sophos Firewall, Ubiquiti UniFi Gateway, OPNsense.
  
- **In ambito domestico o Plug & Play:** pfSense, OPNsense, Ubiquiti UniFi Gateway, TP-Link Omada.

---
[[Router]]
[[Switch]]
[[Ethernet]]
[[LAN (Local Area Network)]]
[[Internet]]
[[Port numbers]]