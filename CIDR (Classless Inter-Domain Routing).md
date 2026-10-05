---
date: 2026-07-09T19:59:00
tags:
  - informatica
  - pubblico
---
# CIDR (Classless Inter-Domain Routing)
---
Un sistema di notazione degli indirizzi IP introdotto nel 1993 per superare la rigidità e l'enorme spreco di spazio causato dal vecchio sistema basato sulle [[Classi di indirizzi IP (Classful Routing)]].

### Come funziona?
Nel vecchio sistema a classi, la rete a cui apparteneva un indirizzo IP determinava automaticamente la sua subnet mask. Per esempio, un indirizzo che iniziava con `10.X.X.X` apparteneva alla classe A e utilizzava automaticamente la maschera `255.0.0.0`.

CIDR elimina questa rigidità permettendo di decidere quanti bit dell'indirizzo IP devono essere utilizzati per identificare la rete, indipendentemente dalla vecchia classe a cui apparteneva l'indirizzo.

Per indicare questa suddivisione utilizzi la notazione slash, es. 192.168.1.10/24. Partendo dal fatto che un indirizzo IPv4 è lungo 32 bit, il numero dopo lo slash indica:

- Quanti di questi 32 bit sono riservati per identificare la rete.
- Quanti i bit rimanenti utilizzati per identificare gli host di quella rete.
  
Questo tipo di allocazione è più efficiente e flessibile rispetto alle vecchie classi di indirizzi, perchè ti permette di riservare in maniera più granulare gli indirizzi che ti servono: se hai bisogno di 1000 indirizzi, usi una `/22` da 1022 indirizzi invece che un'intera classe B da 65.534.

### Come si calcola il numero di indirizzi utili?
Il numero di indirizzi disponibili dipende dai bit lasciati alla parte degli host:

- Abbiamo visto che un indirizzo IPv4 è composto da 32 bit.
  
- Calcoliamo quanti bit rimangono per gli host così:

```
Bit per gli host = 32 - bit per la rete
```

- Da questi bit ricaviamo il numero totale di indirizzi:

$$  
\text{Indirizzi totali} = 2^{\text{bit host}}  
$$

- Nelle normali reti IPv4 però, il primo indirizzo identifica la rete e l'ultimo è riservato al broadcast, quindi tocca toglierli dal conteggio totale degli indirizzi utilizzabili per gli host:

$$  
\text{Indirizzi utilizzabili} = 2^{\text{bit host}} - 2  
$$

Per fare un esempio, una rete `/24` lascia 8 bit per gli host:

$$  
2^8 = 256  
$$

Quindi:

$$  
256 - 2 = 254  
$$

Una `/24` dispone quindi di 254 indirizzi utilizzabili dagli host.

---
