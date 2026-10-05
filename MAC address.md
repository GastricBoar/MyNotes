---
date: 2024-11-28
tags:
  - informatica
  - pubblico

---
# MAC address
***
Un indirizzo MAC (Media Access Control), anche detto indirizzo fisico, è un piccolo codice che identifica univocamente ogni scheda di rete. Viene assegnato in fase di produzione dal produttore della scheda di rete.

##### **Struttura**

Ha un dimensione di 48 bit, ed è composto da 6 gruppi di due cifre esadecimali:

```
00:1A:2B:3C:4D:5E
```

È diviso in due gruppi di cifre:

- **OUI (Organizationally Unique Identifier)**: i primi 24 bit, assegnati dallo standard IEEE; identificano il produttore della scheda di rete.
- **Identificatore NIC (Network Interface Controller):** gli ultimi 24 bit, sono assegnati dal produttore e distinguono ogni dispositivo prodotto.

Gli indirizzi MAC dovrebbero essere unici a livello globale.

Per scoprire il nostro indirizzo MAC, basta aprire un terminale e digitare il comando ipconfig /all.
***
Gli indirizzi MAC sono parte di un [[Frame]].

Gli indirizzi MAC identificano un host all'interno di una [[LAN (Local Area Network)]].

Gli indirizzi MAC fanno parte dello standard [[Ethernet]].

Un indirizzo MAC viene detto "fisico" perchè assegnato in modo permanente a una scheda rete dalla sua casa produttrice, un [[Indirizzo IP (Internet Protocol)]] è detto "logico" perchè assegnato dinamicamente e a livello software, u




