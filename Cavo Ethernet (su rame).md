---
date: 2026-09-22
tags:
  - informatica
  - pubblico
---
# Cavo Ethernet (su rame)
---
Cavo in rame utilizzato per collegare tra loro i dispositivi di una rete locale (LAN).

### Come funziona?
Due dispositivi collegati da un cavo Ethernet comunicano tramite segnali elettrici.

Un cavo Ethernet ha dentro 8 fili di rame isolati, intrecciati a due a due per formare 4 coppie:

- **Coppia arancione:** bianco-arancione, arancione.
- **Coppia verde:** bianco-verde, verde.
- **Coppia blu:** bianco-blu, blu.
- **Coppia marrone:** bianco-marrone, marrone.

<img src="Utilities/Media/Pasted%20image%2020260923205048.png" alt="Pasted image 20260923205048.png" width="460">

Intrecciare i fili di rame (twisted pair) protegge il segnale elettrico da interferenze esterne e disturbi generati dai fili vicini.

Il cavo termina su entrambe le estremità con un connettore a scatto, chiamato RJ45, dove i fili incontrano 8 contatti metallici dorati chiamati pin e numerati da 1 a 8. Ogni pin tocca un singolo filo e fa passare il segnale elettrico verso la porta del dispositivo.

Un cavo Ethernet non usa sempre tutti e 8 i fili di rame, per esempio nelle reti Fast Ethernet (da 100 Mbps) ne sfrutta soltanto 4 (in due coppie) collegati a 4 pin specifici:

- **Pin 1 e 2:** usati per trasmettere dati (Tx, che sta per "Transmit").
  
- **Pin 3 e 6:** usati per ricevere dati (Rx, che sta per "Receive").

I PIN 4, 5, 7 e 8 nelle reti a 100 Mbps rimangono inutilizzati, ma vengono usati tutti e 8 in reti Gigabit (da 1000 Mbps) o per alimentare dispositivi via PoE.

<img src="Utilities/Media/Pasted%20image%2020260923205130.png" alt="Pasted image 20260923205130.png" width="463">

### Tipi di porte di rete
Le porte RJ45 sui dispositivi di rete si dividono in due categorie, in base a come sono collegati internamente i loro circuiti elettronici.

- **Porte MDI (Medium Dependent Interface):** su PC, server e router; usano i pin 1 e 2 per trasmettere, e i pin 3 e 6 per ricevere.
  
- **Porte MDI-X (Medium Dependent Interface Crossover):** su switch e hub; hanno i circuiti invertiti di fabbrica, quindi usano i pin 1 e 2 per ricevere e i pin 3 e 6 per trasmettere.

Si chiama Medium Dependent Interface perché l'interfaccia fisica (la porta) è progettata per dipendere dalle caratteristiche del mezzo di trasmissione (il cavo), adattando la propria elettronica per ricevere e inviare segnali elettrici dai pin del connettore.

Tieni a mente che al giorno d'oggi questa distinzione fisica è diventata quasi irrilevante grazie all'Auto-MDIX (Automatic Medium-Dependent Interface Crossover): 

- è una tecnologia integrata in quasi tutte le schede di rete moderne che rileva automaticamente il tipo di cavo collegato e la disposizione dei pin dell'altro dispositivo.
- Se rileva che la trasmissione e la ricezione sono errate, fa in modo che la porta riassegni via software la funzione dei pin, in tempo reale.

È comunque importante a livello di teoria delle reti conoscere la differenza tra porte di rete di vario tipo.

### Tipi di cavo
Due tipi principali di cavo Ethernet, in base a come sono connessi ai PIN i fili di rame interni:

#### Cavo Crossover
Collega dispositivi dello stesso tipo (un PC a un PC, uno switch a uno switch, un router a un router etc.).

Incrocia così i fili tra le due estremità del cavo:

- Il pin 1 di un'estremità va al pin 3 dell'altra estremità.
- Il pin 2 di un'estremità va al pin 6 dell'altra estremità.

In questo modo il canale di trasmissione del primo PC è collegato direttamente al canale di ricezione del secondo PC.

#### Cavo Straight-Through
Collega dispositivi di tipo diverso (un PC a uno switch, un router a uno switch etc.).

Mantiene lo stesso ordine dei fili su entrambe le estremità del cavo:

- Il pin 1 di un'estremità va al pin 1 dell'altra estremità.
- Il pin 2 di un'estremità va al pin 2 dell'altra estremità.
- Il pin 3 di un'estremità va al pin 3 dell'altra estremità.
- Il pin 6 di un'estremità va al pin 6 dell'altra estremità.

In questo modo il canale di trasmissione del PC si collega direttamente al canale di ricezione dello switch, che ha già i pin invertiti all'interno della sua porta.

### Standard di cablaggio
Due standard per stabilire l'ordine con cui gli 8 fili di rame vengono collegati ai pin del connettore: T568A e T568B.

<img src="Utilities/Media/Pasted%20image%2020260923205241.png" alt="Pasted image 20260923205241.png" width="473">

Come vedi la differenza sta nell'ordine in cui vengono disposte le coppie verdi e arancioni:

- Nel T568A hai arancione al pin 3, bianco-arancione al pin 6, verde al pin 7, bianco-verde al pin 8.

- Nel T568B hai verde al pin 3, bianco-verde al pin 6, arancione al pin 7, bianco-arancione al pin 8.

Per realizzare un cavo straight-through, utilizzi lo stesso standard alle due estremità, es. T568B-T568B o T568A-T568A

Per realizzare un cavo crossover utilizzi invece standard diversi alle due estremità, es. T568B-T568A, in modo da invertire le coppie utilizzate per trasmissione e ricezione.

Nelle installazioni Ethernet moderne è molto comune utilizzare T568B, ma entrambi gli standard sono validi.

---
[[Ethernet]]
[[PoE (Power Over Ethernet)]]
[[Router]]
[[Switch]]
