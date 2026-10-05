---
date: 2026-08-04
tags:
  - informatica
  - pubblico

---
# DMZ (Demilitarized Zone)
---
Una sottorete fisica o logica situata tra LAN interna e WAN\Internet. Espone in sicurezza servizi interni (server web, server email, server DNS o VPN) verso l'esterno, in modo che un'eventuale compromissione non permetta all'attaccante di accedere alla LAN.

### Come funziona?
Un firewall gestisce la DMZ dividendo la rete in tre zone, con diversi livelli di sicurezza:

- **Rete Interna (LAN):** la zona ad altissima sicurezza (PC, database, controller di dominio etc.).
- **DMZ:** zona a media sicurezza (server accessibili da Internet).
- **Internet (WAN):** zona a sicurezza zero, la rete pubblica.

Da qui si applicano delle regole asimmetriche tra le zone:

- **Da Internet a DMZ:** consentito solo per le porte e i servizi pubblici specifici (es. HTTP/HTTPS).
  
- **Da DMZ a LAN:** bloccato, impedisce movimenti laterali; se un server in DMZ viene hackerato, l'attaccante rimane isolato nella DMZ e non può arrivare in LAN.
  
- **Da LAN a DMZ:** consentito per scopi di gestione, manutenzione e aggiornamento da parte degli amministratori di rete.

### Tipologie di Implementazione
Esistono due configurazioni principali per la creazione di una DMZ:

- **Firewall singolo (a tre porte):** Un unico firewall fisico con tre interfacce di rete distinte (WAN, LAN, DMZ). È la soluzione più comune in piccoli contesti.
  
- **Doppio firewall:** due firewall posti in cascata con la DMZ chiusa nel mezzo. Il primo firewall gestisce il traffico verso Internet, mentre il secondo (spesso di un produttore diverso per ridurre la probabilità di vulnerabilità identiche) protegge la LAN dalla DMZ. È la scelta adottata in ambienti ad alta sicurezza.

---
[[Router]]