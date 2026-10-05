---
date: 2025-01-16
tags:
  - informatica
  - pubblico

---
# Wi-Fi
---
Un insieme di tecnologie di comunicazione wireless per [[WLAN (Wireless Local Area Network)]], basato sugli standard IEEE 802 ([[IEEE 802.11]])

Ricorda che Wi-Fi è un marchio commerciale, della Wi-Fi Alliance. Come conseguenza, l'uso del termine "Wi-Fi Certified" è consentito solo ai prodotti che completano i test di certificazione e operabilità.

### Come funziona?
Il Wi-Fi trasmette dati nell'aria utilizzando onde radio. Per capire come si traducono queste onde in velocità, copertura e stabilità, serve analizzare un paio di elementi.

### Le bande di frequenza
Una banda è la porzione di spettro radio utilizzata per la trasmissione. Ad oggi esistono tre bande principali:

| **Caratteristica**             | **Banda 2.4 GHz**                               | **Banda 5 GHz**                               | **Banda 6 GHz (Wi-Fi 6E/7)**                   |
| ------------------------------ | ----------------------------------------------- | --------------------------------------------- | ---------------------------------------------- |
| **Velocità**                   | fino a 600 Mbps                                 | fino a 9.6 Gbps                               | fino a 46 Gbps                                 |
| **Raggio di copertura**        | fino a 45 metri                                 | fino a 15 metri                               | Principalmente stessa stanza)                  |
| **Penetrazione ostacoli**      | Supera muri spessi                              | Supera 1-2 pareti                             | Bloccata facilmente dai muri                   |
| **Congestione e interferenze** | Molto alta (altri router, Bluetooth, microonde) | Bassa (molti canali disponibili)              | Quasi nulla (spettro dedicato e pulito)        |
| **Latenza**                    | Media-alta                                      | Bassa                                         | Bassissima                                     |
| **Compatibilità**              | Universale (tutti i dispositivi e IoT)          | Elevata (quasi tutti i dispositivi moderni)   | Limitata (solo dispositivi recenti Wi-Fi 6E\7) |
| **Uso ideale**                 | Domotica, navigazione base, lunga distanza      | Streaming 4K, videochiamate, lavoro d'ufficio | Gaming online, visori VR/AR, streaming 8K      |
### Canali Wi-Fi
Sono porzioni di frequenza all'interno di una banda Wi-Fi sulle quali i dispositivi trasmettono e ricevono dati. Più reti usano porzioni di frequenza sovrapposte, maggiore può essere l'interferenza.

Per esempio, la banda 2,4 GHz è suddivisa in diversi canali:

| Canale | Frequenza centrale |
| -----: | -----------------: |
|      1 |           2412 MHz |
|      2 |           2417 MHz |
|      3 |           2422 MHz |
|      4 |           2427 MHz |
|      5 |           2432 MHz |
|      6 |           2437 MHz |
|      7 |           2442 MHz |
|      8 |           2447 MHz |
|      9 |           2452 MHz |
|     10 |           2457 MHz |
| **11** |           2462 MHz |
|     12 |           2467 MHz |
|     13 |           2472 MHz |

Ogni canale ha una sua ampiezza, che rappresenta la quantità di frequenza usata per singolo canale. Più il canale è largo, più dati passano contemporaneamente:

  * **20 MHz:** ampiezza base; è stabile e copre distanze maggiori.
  * **40-80 MHz:** standard per streaming e gaming.
  * **160-320 MHz:** utilizzata da Wi-Fi 6 e Wi-Fi 7 per trasferimenti ultra-veloci; richiede segnale pulito e vicinanza al router.

I canali sono parzialmente sovrapposti. Per questo, con una larghezza di canale di 20 MHz, i canali tipicamente utilizzati sono 1, 6, 11; sono sufficientemente distanziati da ridurre al minimo la sovrapposizione tra reti.

### Standard Wi-Fi
Sono regole tecniche definite dall'IEEE, che stabiliscono come i dati vengono codificati e trasmessi tramite Wi-Fi. Ogni generazione introduce miglioramenti in termini di velocità, efficienza, gestione delle interferenze e numero di dispositivi gestibili. Gli standard Wi-Fi si sono evoluti nel tempo, ma fanno tutti parte della famiglia IEEE 802.11:

| Generazione  | Standard | Anno | Banda           | Velocità teorica max | Nome     |
| ------------ | -------- | ---: | --------------- | -------------------: | -------- |
| **Wi-Fi 1**  | 802.11b  | 1999 | 2,4 GHz         |              11 Mbps | Wi-Fi 1  |
| **Wi-Fi 2**  | 802.11a  | 1999 | 5 GHz           |              54 Mbps | Wi-Fi 2  |
| **Wi-Fi 3**  | 802.11g  | 2003 | 2,4 GHz         |              54 Mbps | Wi-Fi 3  |
| **Wi-Fi 4**  | 802.11n  | 2009 | 2,4 / 5 GHz     |             600 Mbps | Wi-Fi 4  |
| **Wi-Fi 5**  | 802.11ac | 2013 | 5 GHz           |            ~6,9 Gbps | Wi-Fi 5  |
| **Wi-Fi 6**  | 802.11ax | 2019 | 2,4 / 5 GHz     |            ~9,6 Gbps | Wi-Fi 6  |
| **Wi-Fi 6E** | 802.11ax | 2021 | 2,4 / 5 / 6 GHz |            ~9,6 Gbps | Wi-Fi 6E |
| **Wi-Fi 7**  | 802.11be | 2024 | 2,4 / 5 / 6 GHz |             ~46 Gbps | Wi-Fi 7  |

Uno standard può essere retrocompatibile con i precedenti; questo perchè un [[WAP (Wireless Access Point)]] o un [[SOHO router (Small Office Home Office)]] possono contenere radio che viaggiano su [[Bande di frequenza]] utilizzate dai loro predecessori; è il caso dello standard 802.11n, retrocompatibile sia con il 802.11b che con l'802.11a perchè ha due radio che viaggiano su quelle due bande.

Lo standard 802.11n ha introdotto una tecnologia chiamata [[MIMO (Multiple Input Multiple Output)]]

### Crittografia di una rete Wi-Fi
Di vari tipi:

- [[WEP (Wired Equivalent Privacy)]]

---
