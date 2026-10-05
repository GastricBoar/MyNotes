---
date: 2025-01-16
tags:
  - informatica
  - pubblico

---
# WAP (Wireless Access Point)
---
Un dispositivo di rete che consente a dispositivi wireless di connettersi a una rete cablata. Fa da ponte tra una rete cablata e una rete wireless, il tutto tramite tecnologie wireless.

<img src="Utilities/Media/Pasted%20image%2020250116120711.png" alt="Pasted image 20250116120711.png" width="293">

Visivamente e strutturalmente è molto semplice: un'entrata per l'alimentazione e un'entrata per il cavo ethernet. Molto spesso non hanno nemmeno il cavo di alimentazione, la corrente arriva al dispositivo direttamente tramite tecnologia [[PoE (Power Over Ethernet)]], ammettendo che anche lo switch sia PoE-capable.

Attenzione, perchè molto spesso capita di guardare un [[SOHO router (Small Office Home Office)]] e pensare sia un access point solo perchè ha delle antenne e un cavo ethernet collegato; non è così, quello è un dispositivo che ha al suo interno più strumenti (tra cui un access point), ma in contesti aziendali più estesi se hai bisogno di un access point, compri un access point e basta.

### Ma come faccio a capire come coprire al meglio lo spazio di una stanza?
Dovessi trovarti a casa, lo faresti ad occhio con un [[SOHO router (Small Office Home Office)]] e i WAP o dei ripetitori.

Nel caso degli uffici o di scenari industriali invece, esistono dei software di analisi wireless; sono molto costosi, ma questo tipo di software ti permette di simulare l'installazione di questi dispositivi in una planimetria con tanto di heatmap del segnale propagato. 

### Come configuro una stessa rete su più access points?
O lo fai manualmente, altrimenti ti compri uno switch con funzionalità WLAN, che ti permette di gestire facilmente una grossa rete composta da tanti switch, e relativo captive portal.

---
[[Antenna]]
[[AAA (Authentication, Authorization, Accounting)]]