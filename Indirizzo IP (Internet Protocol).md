---
date: 2024-12-02
tags:
  - informatica
  - pubblico

---
# Indirizzo IP (Internet Protocol)
***
Anche detto indirizzo logico, è un identificativo numerico assegnato a un dispositivo all'interno di una rete, descrive la [[LAN (Local Area Network)]] a cui appartieni.

Visivamente un indirizzo IP assomiglia a questo:
#### `192.158.1.38` oppure `66.94.29.13`

Una stringa di quattro numeri separata da tre punti, ognuno di questi quattro numeri viene chiamato un **ottetto**. 
### **Perché si chiama ottetto?**
Quelli sono numeri decimali, gli umani leggono facilmente i numeri decimali, ma i computer no; i computer leggono i numeri binari, e ognuna di quelle cifre che tu leggi in sistema decimale equivale a una combinazione di otto cifre binarie. Ogni cifra binaria equivale a un bit, e otto bit equivalgono a 1 byte; da qui viene fuori che un indirizzo IP di questo tipo ha una dimensione di 4 bytes, o 32 bits.

![Pasted image 20241218212409.png](Utilities/Media/Pasted%20image%2020241218212409.png)

### **Come faccio a convertire quel numero in binario?**
[Così.](https://youtu.be/ThdO9beHhpA?feature=shared&t=100)

### **Perchè quattro ottetti e non dieci?**
Ogni indirizzo IP è formato da quattro ottetti, e ogni ottetto può assumere un valore da 0 a 255. Vuoi sapere il perchè di questa decisione? [qui](https://www.youtube.com/watch?v=17GtmwyvmWE&feature=share&t=26m18s) trovi un video molto interessante in cui Vint Cerf (considerato il fondatore di [[Internet]] per come lo conosciamo) spiega perchè un [[Indirizzo IP (Internet Protocol)]] abbia quattro ottetti e perchè ognuno di loro contenga un valore da 0 a 255.

### **In che modo questi numeri identificano una rete?**
Immagina avere tante [[LAN (Local Area Network)]] sparse e isolate per l'America, adesso immagina voler costruire un sistema che permetta di far comunicare tutte queste LAN tra loro.

Cosa fai a questo punto? cominci ad assegnare un numero a ogni [[Router]] che separa queste LAN: al router in Texas diamo il 10, a quello in California diamo il 7, a quell'altro di New York diamo il 3 e così via.

Mettiamo però che la costa del golfo in Texas voglia un suo router, sai cosa facciamo? lo colleghiamo al router 10 e gli diamo un indirizzo IP che faccia riferimento al router principale, qualcosa tipo 10.1. 

Mettiamo però che l'università della costa del golfo in Texas voglia un suo router, a questo punto si fa assegnare un indirizzo IP che assomiglia a 10.1.13.

Un povero disgraziato lì vicino ha una baracca e anche lui vuole il suo router, quindi si fa assegnare un indirizzo IP come 10.1.13.23.

Ecco, questi sono chiamati **indirizzi IP pubblici**, e nel sistema di indirizzamento IPv4 sono limitati a 4,294,967,296 indirizzi unici.

### **Ma chi è che smercia questi indirizzi?**
Non puoi semplicemente scegliere il tuo IP, a distribuire e assegnare gli indirizzi IP pubblici è una società chiamata [[IANA (Internet Assigned Number Authority)]] (https://it.wikipedia.org/wiki/Internet_Assigned_Numbers_Authority).

### **Esistono quindi degli indirizzi IP privati?**
Tornando all'esempio del disgraziato con la baracca di prima: mettiamo che il disgraziato abbia quattro cellulari e tre computer, come fa a identificare ognuno di loro con un indirizzo logico? ecco, qui non è necessario che ogni dispositivo all'interno della sua LAN abbia un indirizzo IP pubblico, quindi si usa un indirizzo IP privato. 

Ci sono delle differenze tra un indirizzo IP pubblico e uno privato ([approfondisci qui](https://www.youtube.com/watch?v=po8ZFG0Xc4Q)):

![Pasted image 20241219212206.png](Utilities/Media/Pasted%20image%2020241219212206.png)

Un indirizzo privato assomiglia a 192.158.1.38, mentre uno pubblico a 66.94.29.13.
Se esegui un ipconfig da terminale, troverai il tuo indirizzo provato; per trovare il tuo indirizzo pubblico, che è anche quello con cui tutti i tuoi dispositivi di casa escono dalla tua LAN, puoi usare uno di quei siti tipo "What Is My IP".

### **Classi di indirizzi IP**
Un sistema usato per categorizzare gli indirizzi in base alla quantità di reti e dispositivi che posson essere gestiti:

| **Caratteristica**              | **Classe C**    | **Classe B**               | **Classe A**                |
| ------------------------------- | --------------- | -------------------------- | --------------------------- |
| **Numeri che possono cambiare** | solo l'ultimo   | gli ultimi due             | gli ultimi tre              |
| **Esempio**                     | 192.168.0.x     | 172.16.x.x                 | 10.x.x.x                    |
| **Host gestibili**              | 254             | 65.534                     | 16.777.214                  |
| **Uso tipico**                  | Piccole aziende | Medie aziende e università | Grandi organizzazioni e ISP |
| **Range del primo ottetto**     | 1-126           | 128-191                    | 192-223                     |
| **[[Subnet mask]] predefinita** | 255.0.0.0       | 255.255.0.0                | 255.255.255.0               |

Adesso, se provi a visualizzare il tuo IP pubblico ti accorgerai che è un indirizzo di classe A, e subito dopo ti dirai "ma io non sono una grande organizzazione, sono un onesto privato! perchè non ho un indirizzo di classe C?"; ecco, devi capire che il tuo ISP ha comprato quegli indirizzi IP in blocco, quindi lui li compra come indirizzi di classe A anche se poi li dà a te che sei un individuale disgraziato.

***
Utilizziamo un indirizzo IP per comunicare con dispositivi al di fuori di una [[LAN (Local Area Network)]].

Un indirizzo IP è detto "logico" perchè assegnato dinamicamente e a livello software, un [[MAC address]] viene detto "fisico" perchè assegnato in modo permanente a una scheda rete dalla sua casa produttrice.
