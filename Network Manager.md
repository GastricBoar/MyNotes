---
date: 2026-11-11-20-30
tags:
  - informatica
  - linux
  - pubblico
---
# Network Manager
---
Software che gestisce la configurazione e il funzionamento delle connessioni di rete in Linux.

### Come funziona?
Un sistema Linux può avere diverse interfacce di rete, ognuna con le proprie configurazioni IP, gateway e DNS; potresti per esempio avere un'interfaccia Ethernet, una Wi-Fi e tanto altro.

Volendo, tu puoi intervenire manualmente su interfacce e parametri di rete, tipo così:

- Usi `ip a add 192.168.35.2 dev enb10s0` per assegnare un indirizzo IP a una scheda di rete.
- Assegni un DNS.
- Assegni un gateway.

Il problema di questo approccio è che al primo riavvio perdi quella configurazione, perchè attiva solo a runtime. Dovresti quindi riproporla a ogni avvio, il che va anche bene se hai tempo, voglia, e una sola interfaccia di rete, ma pensa invece gestirne dieci: la questione diventa laboriosa e complicata.

I network managers rispondono a questa esigenza: automatizzano configurazione e controllo delle tue connessioni di rete. Puoi farci cose come:

- Attivare e disattivare interfacce di rete.
- Assegnare indirizzi IP, tramite DHCP o configurazione statica.
- Configurare gateway e DNS.
- Tanto altro.

Invece che star lì a configurare parametri tutto il giorno a ogni riavvio, puoi usare un network manager che conserverà le impostazioni per applicarle quando serve.

Per fare alcuni esempi di network manager:

- **NetworkManager**: molto diffuso nei sistemi desktop Linux, ti permette di gestire le connessioni tramite interfaccia grafica o terminale (nmcli).
  
- **systemd-networkd**: servizio di systemd dedicato alla configurazione e gestione delle interfacce di rete, è particolarmente utilizzato nei server.

- **ConnMan**: una soluzione leggera, pensata soprattutto per sistemi embedded e dispositivi con risorse limitate.

---
[[systemd]]