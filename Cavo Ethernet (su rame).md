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

<img src="Utilities/Media/Pasted%20image%2020260923205048.png" alt="Pasted image 20260923205048.png" width="419">

Intrecciare i fili di rame (twisted pair/doppino intrecciato) protegge il segnale elettrico da interferenze esterne e disturbi generati dai fili vicini.

### Schermatura del cavo
Un cavo lo schermi con uno strato conduttivo che protegge il segnale dalle interferenze; in base alla presenza o alla disposizione di questo strato, i cavi a doppino intrecciato si dividono in più tipologie:

- **Unshielded Twisted Pair (UTP):** non è schermato, i singoli fili di rame sono avvolti da una guaina di materiale isolante (tipicamente plastica, isolante significa che non conduce corrente, non che schermi nulla) e poi racchiusi in una guaina esterna.
  
- **Shielded Twisted Pair (STP):** schermato, tra i fili di rame avvolti dalla guaina e l'esterno del cavo ci sta uno strato di schermatura a proteggerlo da interferenze:

<img src="Utilities/Media/Pasted%20image%2020261011223209.png" alt="Pasted image 20261011223209.png" width="285">

Se vuoi conoscere una chicca in sicurezza delle comunicazioni, vedi [[Intercettazioni TEMPEST]].

### Tipi di conduttore
Il rame all'interno di ciascun doppino può essere predisposto in maniera diversa a seconda dell'utilizzo che ne si fa:

- **Cavi stranded:** il rame all'interno dei cavettini viene scomposto in tanti fili, garantisce maggiore flessibilità e resistenza nei casi in cui il cavo deve essere mosso molto, es. un cavo Ethernet che arriva dalla presa muro a un PC.
  
- **Cavi solid core:** dentro al doppino c'è un filo di rame duro e puro, tutto d'un pezzo. È molto resistente e si rompe con meno probabilità, è utile a scenari in cui il cavo si muove poco, es. un cavo che da uno [[Switch]] passa attraverso i muri e arriva a un [[Patch panel]].

<img src="Utilities/Media/Pasted%20image%2020261011224154.png" alt="Pasted image 20261011224154.png" width="417">

### Cavi Direct-buried (DBC)
Specificatamente progettati per essere interrati, vedi [[Cavo Direct-Buried (DBC)]].

### Il connettore
Il cavo termina su entrambe le estremità con un connettore a scatto, chiamato RJ-45, dove i fili incontrano 8 contatti metallici dorati chiamati pin e numerati da 1 a 8. Ogni pin tocca un singolo filo e fa passare il segnale elettrico verso la porta del dispositivo.

Non è da confondere con il connettore RJ-11, che è solitamente il connettore di quel cavo che parte della borchia del muro per arrivare al router ("il filo del telefono" in volgare). A differenza dell'RJ-45 è piccolo e usa solo quattro o sei punti di contatto:

<img src="Utilities/Media/Pasted%20image%2020261011224525.png" alt="Pasted image 20261011224525.png" width="483">

Anche i connettori possono essere schermati, tipo questo:

<img src="Utilities/Media/Pasted%20image%2020261011223502.png" alt="Pasted image 20261011223502.png" width="285">

### I pin
Un cavo Ethernet non usa sempre tutti e 8 i fili di rame, per esempio nelle reti Fast Ethernet (da 100 Mbps) ne sfrutta soltanto 4 (in due coppie) collegati a 4 pin specifici:

- **Pin 1 e 2:** usati per trasmettere dati (Tx, che sta per "Transmit").
  
- **Pin 3 e 6:** usati per ricevere dati (Rx, che sta per "Receive").

I PIN 4, 5, 7 e 8 nelle reti a 100 Mbps rimangono inutilizzati, ma vengono usati tutti e 8 in reti Gigabit (da 1000 Mbps) o per alimentare dispositivi via PoE.

In reti da almeno 1000 Mbps vengono usati i pin nelle seguenti coppie: 1-2, 3-6, 4-5, 7-8.

In un collegamento a 1Gbps vengono usate tutte le coppie, che trasmettono e ricevono allo stesso tempo (full duplex).

<img src="Utilities/Media/Pasted%20image%2020260923205130.png" alt="Pasted image 20260923205130.png" width="463">

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

### I CAT ratings (Category Ratings)
Categorie che classificano la prestazione dei cavi su indici come velocità, distanza e applicazione. La categoria del cavo contribuisce a determinare lo standard [[Ethernet]] supportato. Una tabella:

| Categoria | Anno di introduzione | Velocità massima             | Distanza massima                        | Schermatura              | Utilizzo tipico                               |
| --------- | -------------------- | ---------------------------- | --------------------------------------- | ------------------------ | --------------------------------------------- |
| CAT 5     | 1995                 | 100 Mbps                     | 100 metri                               | Non schermato (UTP)      | Reti domestiche e aziendali base.             |
| CAT 5e    | 2001                 | 1 Gbps                       | 100 metri                               | Non schermato (UTP)      | Standard per reti Gigabit Ethernet.           |
| CAT 6     | 2002                 | 1 Gbps (10 Gbps fino a 55 m) | 100 metri (1 Gbps) / 55 metri (10 Gbps) | UTP o schermato (STP)    | Data center, reti aziendali avanzate.         |
| CAT 6A    | 2008                 | 10 Gbps                      | 100 metri                               | Sempre schermato (STP)   | Reti ad alta velocità e bassa latenza.        |
| CAT 7     | 2010                 | 10 Gbps                      | 100 metri                               | Sempre schermato (S/FTP) | Applicazioni professionali e industriali.     |
| CAT 8     | 2016                 | 25–40 Gbps                   | 30 metri                                | Sempre schermato (S/FTP) | Data center, connessioni a server e backbone. |

Questi dati li trovi sulla scatola del cavo, ma attenzione: i furbi furbi venditori potrebbero utilizzare un loro sistema interno di CAT che non corrisponde in maniera diretta alle vere diciture CAT, es. il CAT 6e di una certa compagnia di cavi potrebbe corrispondere al CAT 6 dello standard internazionale, quindi è compito tuo tradurre l'indice del venditore nel suo corrispettivo internazionale.

### Standard Ethernet su rame
Qui una tabella:

| Velocità | Nome comune         | Standard IEEE | Denominazione tecnica | Lunghezza massima | Pin utilizzati su connettore |
| -------- | ------------------- | ------------- | --------------------- | ----------------- | ---------------------------- |
| 10 Mbps  | Ethernet            | IEEE 802.3i   | 10BASE-T              | 100 metri         | 4 (1, 2, 3, 6)               |
| 100 Mbps | Fast Ethernet       | IEEE 802.3u   | 100BASE-TX            | 100 metri         | 4 (1, 2, 3, 6)               |
| 1 Gbps   | Gigabit Ethernet    | IEEE 802.3ab  | 1000BASE-T            | 100 metri         | 8 (1–8)                      |
| 10 Gbps  | 10 Gigabit Ethernet | IEEE 802.3an  | 10GBASE-T             | 100 metri         | 8 (1–8)                      |

Quella denominazione tecnica la distingui in tre parti:

- **1000:** è la velocità di trasmissione.
- **BASE:** trasmissione in banda base, approfondisci se vuoi e confronta le differenze con la trasmissione a banda passante.
- **T:** utilizza un cavo a doppino intrecciato in rame (quindi twisted pair).

Da qui viene che 1000BASE-T è un collegamento che trasmette dati a 1Gbps su cavo a doppino intrecciato in rame.

### Il plenum rating
Questo è lo standard di classificazione che definisce la resistenza al fuoco del cavo:

- **Cavi in PVC (Non-Plenum Rated):** per installazioni generali al di fuori di un controsoffitto. Sono economici, ma offrono resistenza al fuoco limitata e possono emettere fumi tossici quando bruciano.

- **Cavi Riser-Rated (CMR):** progettati per installazioni verticali tra i piani di un edificio, in un contropavimento. Resistono meglio alla propagazione del fuoco rispetto ai cavi in PVC standard, e costano di più rispetto a loro.

- **Cavi Plenum-Rated (CMP):** progettati per controsoffitti, offrono maggiore resistenza alla propagazione del fuoco e limitano la produzione di fumi, sono generalmente più costosi.

Un "plenum" è un controsoffitto, mentre un "riser" è un contropavimento. 



---
[[Ethernet]]
[[PoE (Power Over Ethernet)]]
[[Router]]
[[Switch]]
[[RJ (Registered Jack)]]
[[Porta di rete Ethernet (su rame)]]