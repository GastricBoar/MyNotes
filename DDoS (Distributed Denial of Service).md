---
date: 2026-09-01
tags:
  - informatica
  - pubblico

---
# DDoS (Distributed Denial of Service)
---
Attacco informatico in cui l'attaccante utilizza molti dispositivi distribuiti per rendere un servizio, un server o una rete inutilizzabile/non disponibile per gli utenti legittimi, consumandone le risorse.

### Come funziona?
L'attaccante prima compromette un grande numero di dispositivi, come computer, smartphone, router o dispositivi IoT, installando malware che gli permette di controllarli da remoto. Questi dispositivi compromessi vengono chiamati zombie e, insieme, formano una botnet.

Quando l'attaccante ordina alla botnet di eseguire l'attacco, tutti gli zombie inviano richieste verso il bersaglio. L'obiettivo non è necessariamente rubare dati, ma impedire agli utenti legittimi di utilizzare il servizio.

### Che differenza con il DoS?
Nel DoS l'attacco proviene generalmente da un'unica sorgente, mentre nel DDos viene invece effettuato contemporaneamente da molti dispositivi o una botnet, rendendo più difficile bloccare il traffico.

### Come si previene?
La difesa principale consiste nel limitare e filtrare il traffico diretto verso il servizio, in modo che un attaccante non possa consumarne le risorse facilmente:

- **Usa un firewall:** filtra il traffico indesiderato prima che possa raggiungere il servizio.

- **Usa rate limiting:** limita il numero di richieste che un singolo client può effettuare in un determinato periodo.

- **Distribuisci il carico tramite load balancing:** puoi distribuire le richieste tra più server, evitando che un singolo sistema venga sovraccaricato.

- **Usa protezione DDoS:** esistono servizi specializzati che possono identificare e filtrare il traffico malevolo prima che raggiunga l'nfrastruttura.

- **Monitora il traffico e genera allarmi:** per rilevare picchi anomali di richieste prima che il servizio diventi indisponibile.

---
[[Denial of Service (DoS)]]