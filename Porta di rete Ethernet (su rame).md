---
date: 2026-10-12-21-44
tags:
  - informatica
  - pubblico
---
# Porta di rete Ethernet (su rame)
---
Interfaccia fisica che permette a un dispositivo di rete di collegarsi a una rete Ethernet tramite un cavo in rame e connettore RJ45.

### Come funziona?
Una porta Ethernet contiene contatti metallici che entrano in contatto con gli 8 pin del connettore del cavo, trasmettendo segnali elettrici.

Qui le porte di rete del server di casa ;))

<img src="Utilities/Media/Pasted%20image%2020261012214936.png" alt="Pasted image 20261012214936.png" width="386">

### Tipi di porte di rete
Si dividono in due categorie, in base a come sono collegati internamente i loro circuiti elettronici:

- **Porte MDI (Medium Dependent Interface):** su PC, server, router e firewall; nelle reti fino a 100 Mbps usano i pin 1 e 2 per trasmettere, e i pin 3 e 6 per ricevere. Nelle reti a 1Gbps il problema non si pone in primo luogo, perchè tutte le coppie trasmettono e ricevono allo stesso tempo (full duplex).
  
- **Porte MDI-X (Medium Dependent Interface Crossover):** su switch e hub; hanno i circuiti invertiti di fabbrica, quindi usano i pin 1 e 2 per ricevere e i pin 3 e 6 per trasmettere. Nelle reti fino a 100 Mbps usano i pin 1 e 2 per trasmettere, e i pin 3 e 6 per ricevere. Nelle reti a 1Gbps il problema non si pone in primo luogo, perchè tutte le coppie trasmettono e ricevono allo stesso tempo (full duplex).

Si chiama Medium Dependent Interface perché l'interfaccia fisica (la porta) è progettata per dipendere dalle caratteristiche del mezzo di trasmissione (il cavo), adattando la propria elettronica per ricevere e inviare segnali elettrici dai pin del connettore.

Tieni a mente che al giorno d'oggi questa distinzione fisica è diventata quasi irrilevante grazie all'Auto-MDIX (Automatic Medium-Dependent Interface Crossover): 

- È una tecnologia integrata in quasi tutte le schede di rete moderne, rileva automaticamente il tipo di cavo collegato e la disposizione dei pin dell'altro dispositivo.
  
- Se rileva che la trasmissione e la ricezione sono errate, fa in modo che la porta riassegni via software la funzione dei pin, in tempo reale.

È comunque importante a livello di teoria delle reti conoscere la differenza tra porte di rete di vario tipo.

---
[[Cavo Ethernet (su rame)]]
[[Ethernet]]
[[RJ (Registered Jack)]]