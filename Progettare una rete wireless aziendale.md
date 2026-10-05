---
date: 2025-02-01
tags:
  - informatica
  - pubblico

---
# Progettare una rete wireless aziendale
---
Tirar su una rete [[WLAN (Wireless Local Area Network)]] in un contesto aziendale è diverso da farlo in un contesto privato. A casa potresti comprare un bel [[SOHO router (Small Office Home Office)]] e al massimo qualche ripetitore o dei [[WAP (Wireless Access Point)]], ma in aziende strutturate non è così; ci sono delle cose a cui devi prestare attenzione.

###### **Distribuire il segnale lungo tutta la struttura** 
Esistono dei software di analisi wireless; sono molto costosi, ma questo tipo di software ti permette di simulare l'installazione di questi dispositivi in una planimetria con tanto di heatmap del segnale propagato da ciascun [[Antenna]] e dispositivo di rete.

###### **Configurare i WAP**
Ci sono delle cose di cui dovresti occuparti subito dopo aver installato i tuoi WAP:

- **Imposta un ESSID (Enterprise Service Set Identifier):** è come un SSID, ma invece che assegnarlo a un solo dispositivo di rete, saranno tutti i WAP in massa a prenderlo. È utile perchè potrai esser connesso alla stessa rete anche su grosse distanze.

- **Attiva la funzionalità Isolation:** fa in modo che il tuo dispositivo possa comunicare solo il WAP, e non gli altri dispositivi in rete; tutti i dispositivi potranno navigare tramite il WAP, ma non potranno comunicare tra loro per scambiarsi file o altro.

- **Attiva il rogue AP detection:** immagina se qualcuno arrivasse e connettesse il proprio WAP alla tua rete, sarebbe un rogue AP; questa funzione fa in modo di proteggerti da questi problemi, i WAP in WLAN conosceranno a memoria i [[MAC address]] tra loro, se si unisce un nuovo WAP verrà bloccato o segnalato. A proposito, è utile sempre ricordare cosa stai passando in DHCP ai dispositivi all'interno della tua rete; magari sai di star passando 10.0.0.20-40, ma all'improvviso ritrovi un 32.45.68.79 in rete e ricordando che non fa parte della tua rete lo butti fuori subito (accertandoti però prima che non sia un indirizzo [[APIPA (Automatic Private IP Addressing)]]).

- **Definisci il rate limit:** se necessario, è il limite sulla quantità di traffico passante per il WAP; il parametro può esser definito per l'upstream così come per il downstream.

- **Configura il captive portal:** è il portale che si presenta a ogni utente durante la connessione alla WLAN, chiederà uno username e una password ma può esser configurato per autenticare utenti in altro modo.

Una cosa importante da sapere è che i WAP non devono per forza esser configurati manualmente uno alla volta (significherebbe configurare le utenze su captive portal, impostare gli SSID e tutto il resto); si può preparare una configurazione unica e poi propagarla tramite un [[WLAN Switch]].

###### **Prepararsi al troubleshooting sui problemi**
Ci sono degli strumenti pensati per far troubleshooting su reti wireless e anche sulle [[ISM bands (Industrial, Scientific and Medical Bands)]], per esempio i [[Wi-Fi]] analyzer (si posson scaricare anche da cellulare, e ti saranno utili in alcuni casi).

---
