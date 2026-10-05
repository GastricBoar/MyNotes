---
date: 2026-08-11
tags:
  - informatica
  - pubblico

---
# WEP (Wired Equivalent Privacy)
---
Il primissimo standard di sicurezza per reti Wi-Fi, introdotto nel 1997 sotto lo standard IEEE 802.11. L'obiettivo originario era garantire alla connessione senza fili un livello di riservatezza e protezione equivalente a quello di una rete cablata Ethernet, dove lo scambio dati è intercettabile solo collegando un dispositivo allo switch.

### Come funziona?
In questo modo:

- Imposti una password per la tua rete, la password occupa 40 bit  (nel caso della chiave a 64 bit).
- Il router, per ogni pacchetto inviato, genera altri 24 bit casuali (detto IV, vettore di inizializzazione).
- L'algoritmo RC4 cifra i pacchetti dati trasmessi nell'aria, vengono poi inviati al destinatario.
- Il destinatario riceve il pacchetto cifrato, legge i 24 bit inviati in chiaro e li unisce ai 40 bit della password registrata in memoria, ottenendo la chiave di decifratura.
- Dà la chiave a RC4 per annullare la cifratura e leggere il messaggio originale.


Due modalità di autenticazione alla rete:

  * **Open System:** ti connetti alla rete inserendo la chiave di cifratura WEP. Il router non fa alcuna verifica sulla correttezza della chiave, accetta la connessione di chiunque. Utilizzerà quella chiave per decifrare i messaggi in rete, se non è giusta ciò che ricevi sarà illeggibile.

  * **Shared Key:** ti connetti alla rete inserendo la chiave di cifratura WEP, ma questa volta ne viene verificata subito la correttezza; se non è la chiave giusta, non potrai alla rete in primo luogo.

### Limiti e svantaggi
Ne aveva un paio. 

A differenza degli standard moderni, il WEP imponeva regole matematiche rigide e vincolanti sulla password:

- L'algoritmo usava chiavi di dimensione fissa, 64 bit o 128 bit.
- La chiave poteva essere scritta in caratteri ASCII o esadecimali.
- Un carattere ASCII occupa 8 bit, un carattere esadecimale ne occupa 4.
- Da qui, la chiave doveva essere lunga esattamente 5 caratteri se in ASCII a 64 bit, 13 caratteri se in ASCII a 128 bit, 10 caratteri se in esadecimale a 64 bit, 26 caratteri se in esadecimale a 128 bit.

Oltre questo, Il WEP è affetto da difetti di progettazione crittografica che lo rendono totalmente insicuro:

* **Il vettore di inizializzazione era troppo corto:** con 24 bit le combinazioni possibili si esaurivano rapidamente.

* **La modalità Shared Key esponeva contemporaneamente il testo in chiaro e quello cifrato della sfida**, facilitando il calcolo della chiave da parte degli attaccanti.

## Confronto con gli standard successivi

| Protocollo | Anno | Cifratura  | Lunghezza Password    | Stato                     |
| :--------- | :--- | :--------- | :-------------------- | :------------------------ |
| **WEP**    | 1997 | RC4        | Fissa (5 o 13 car.)   | Obsoleto                  |
| **WPA**    | 2003 | TKIP / RC4 | Variabile (8-63 car.) | Deprecato                 |
| **WPA2**   | 2004 | AES / CCMP | Variabile (8-63 car.) | Sicuro, standard diffuso  |
| **WPA3**   | 2018 | AES / GCMP | Variabile (8-63 car.) | Massima sicurezza attuale |

---
[[Wi-Fi]]
[[WPA (Wi]]