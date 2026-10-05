---
date: 2025-03-11
tags:
  - informatica
  - pubblico

---
# tracert (traceroute)
---
Strumento da riga di comando utilizzato per tracciare il percorso (route) di un pacchetto dati, dalla macchina di origine fino a quella di destinazione.

In Windows ha sintassi `tracert` mentre in Linux e Mac `traceroute`.

Per ogni riga trovi indirizzo IP/nome di dominio del router raggiunto dal pacchetto, e il tempo in millisecondi (ms) impiegato nel raggiungerlo. In questo screen vedi tre record della latenza per ogni riga, sono tre tentativi diversi misurati per garantire affidabilità.

Ogni riga rappresenta un "hop", il salto da un router all'altro.

#### **Cosa me ne faccio?**
Si può utilizzare per tante cose, ma ti faccio qualche esempio pratico:

- **Non riesci a raggiungere un server aziendale:** lancia un tracert verso il server che non riesci a raggiungere. A seconda di dove il traffico viene interrotto puoi ipotizzare quale sia il problema; per esempio: se si interrompe dopo il firewall interno, potrebbe essere una regola firewall incorretta o un server spento.

- **Rallentamenti anomali in navigazione internet:** raggiungere un servizio esterno ti occupa troppo tempo e non sai perchè. In questo caso potresti lanciare un tracert verso quel servizio e appuntare l'hop a partire dal quale riscontri una latenza anomala.


---
[[nslookup (Name Server Lookup)]]

[[ipconfig]]