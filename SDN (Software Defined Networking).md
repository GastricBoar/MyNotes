---
date: 2025-01-15
tags:
  - informatica
  - pubblico

---
# SDN (Software-Defined Networking)
---
Un paradigma di rete che separa la logica di decisione e instradamento (Control Plane) dall'effettivo inoltro dei pacchetti (Data Plane). L'intelligenza della rete viene estratta dai singoli apparati fisici e centralizzata in un software chiamato SDN Controller, rendendo l'infrastruttura di rete programmabile, flessibile e automatizzabile.

## Il contesto
Pensa a una rete tradizionale:

- Ogni apparato elabora decisioni software su dove devono andare i dati, queste sono gestite dalla sua CPU: calcola rotte, gestisce protocolli di rete, applica regole. Si chiama Control Plane.
  
- Allo stesso tempo, la parte hardware riceve bit di dati e li sposta da una porta fisica all'altra, questo è il Data Plane.
  
* Se vuoi applicare una modifica (es. bloccare il traffico tra due subnet), hai bisogno di collegarti in SSH a ogni singolo apparato e digitare regole manualmente, con probabilità di errore umano. Ancora peggio sarebbe ripetere questo lavoro per infrastrutture in cloud, dove crei e distruggi molte VM e container.

## Come funziona?
Un'architettura SDN risolve questa rigidità tradizionale dividendo la rete in due livelli:

* **Control Plane centralizzato** un software unico (SDN Controller) che gestisce la visione globale dell'infrastruttura, calcola percorsi ottimali e definisce le regole di sicurezza. Per fare qualche esempio: Cisco APIC, VMware NSX, Arista CloudVision, Juniper Contrail, OpenDayLight, ONOS, Ryu.
  
* **Data Plane periferico:** gli switch fisici o virtuali diventano esecutori che si limitano a inoltrare i pacchetti eseguendo le istruzioni ricevute dal controller.

Facendo un esempio:

- Hai bisogno di impedire ai computer del reparto Sviluppo di accedere ai server del reparto Contabilità.
  
- In una rete tradizionale ti colleghi a tutti gli appararati in SSH, per applicare le regole di filtro manualmente.
  
- Con SDN imposti una regola logica sulla dashboard del tuo controller SDN, oppure ti crei uno script automatizzato.

- Il controller SDN elabora la topologia della rete, e invia la regola a tutti gli apparati tramite API.

---
[Resources explaining software defined networking (SDN) : r/CompTIA](https://www.reddit.com/r/CompTIA/comments/199ftnl/resources_explaining_software_defined_networking/)