---
date: 2024-12-26
tags:
  - informatica
  - pubblico

---
# APIPA (Automatic Private IP Addressing)
***
Servizio interno ad alcuni sistermi operativi,  assegna automaticamente un [[Indirizzo IP (Internet Protocol)]] a un dispositivo interno a una [[LAN (Local Area Network)]] nel caso in cui il server [[DHCP (Dynamic Host Configuration Protocol)]] non sia raggiungibile; quando il tuo dispositivo prende un IP privato, allora vuol dire che devi sistemare il server DHCP.

Tutti gli indirizzi privati assegnati tramite APIPA hanno range 169.254.0.0 - 169.254.255 e subnet mask 255.255.0.0.
###### **In che modo può interagire con una rete un dispositivo con indirizzo IP privato?**
Può comunicare solamente con i dispositivi all'interno della rete stessa, ma non può raggiungere internet o reti esterne.

###### **"Io non voglio che il mio dispositivo prenda automaticamente un indirizzo IP privato!"** 
In genere è quello di cui hai bisogno, però ci sono dei casi particolari (adesso non ne conosco nessuno) in cui può essere utile che il PC prenda un indirizzo statico piuttosto che un indirizzo privato. Si fa così: [[Sostituire un indirizzo IP privato con uno statico]].
***

