---
date: 2024-12-26
tags:
  - informatica
  - pubblico

---
# DHCP (Dynamic Host Configuration Protocol)
***
Un protocollo di rete che assegna automaticamente [[Indirizzo IP (Internet Protocol)]] e altre configurazioni ai dispositivi in una rete [[LAN (Local Area Network)]].

Come già sai, un dispositivo senza indirizzo IP non riuscirebbe a comunicare con nessun altro all'interno di una rete; un indirizzo IP è necessario.

###### **"Ma io non ricordo mica di aver assegnato un indirizzo IP a nessuno dei miei dispositivi."** 
Ma io gnognegnegne- grande minchione, non lo hai mai dovuto assegnare manualmente perchè il DHCP lo ha fatto per te. Ecco cosa devi sapere:

1. Il DHCP è gestito da un server DHCP.
2. Nel momento in cui un dispositivo (che chiamiamo DHCP client) si connette alla rete, invia una sorta di segnale o chiamata; è come se urlasse a tutti "mi serve un indirizzo IP, presto!".
3. Il server DHCP risponde, gli assegna un indirizzo IP, una [[Subnet mask]] e un default gateway; queste sono le cose di cui ha bisogno per poter comunicare correttamente con gli altri dispositivi in rete.

Immagina se questo meccanismo non esistesse: per collegarti al Wi-Fi della biblioteca dovresti presentarti davanti alla biblotecaria e chiederle "mi ferve fapere il mio indirizzo IP, la mia fubnet mafk e un default gateway".

###### **"Ok, ma dove sta questo server DHCP? non mi sembra di averne uno in casa."** 
Invece ce l'hai, in una rete domestica fa spesso parte del router ([[SOHO router (Small Office Home Office)]]) che ti è stato affidato dal tuo gestore telefonico. Ricorda che essendo a tutti gli effetti un server, il server DHCP ha un suo indirizzo IP.
###### **"Come verifico l'indirizzo IP del DHCP server al quale sono collegato?"** 
Apri il CMD, scrivici dentro `ipconfig /all` e scorri in basso alla scheda di rete che stai utilizzando; in quella scheda troverai l'indirizzo IP del server DHCP al quale sei collegato:

![Pasted image 20241226004521.png](Utilities/Media/Pasted%20image%2020241226004521.png)

###### **"Cosa succede se il mio server DHCP va giù?"** 
Il tuo dispositivo prende un indirizzo IP privato tramite [[APIPA (Automatic Private IP Addressing)]]; risolvi così: [[Risolvere problemi legati al server DHCP]].

###### **Il DHCP range** 
L'intervallo di indirizzi assegnabili dal server. Potremmo configurare il DHCP in modo da assegnare ai dispositivi nella nostra rete un indirizzo IP qualsiasi compreso nel range 192.168.1.100 - 192.168.1.200
###### **Il DHCP lease** 
Il periodo di tempo entro il quale un indirizzo IP assegnato dal server DHCP rimane valido per un dispositivo. Prima della sua scadenza, il dispositivo tenta di rinnovare il lease; se non ci riesce, l'indirizzo torna al pool diventando disponibile per gli altri dispositivi in [[LAN (Local Area Network)]].
###### **Le DHCP reservations** 
Una configurazione che permette di assegnare permanentemente un indirizzo IP a un dispositivo in rete, all'interno di un pool di indirizzi dinamici. Può essere utile per i dispositivi che torna utile abbiano un indirizzo statico (come stampanti, servers, telecamere); in molti casi però non ha senso riservare un indirizzo all'interno del DHCP range, sarebbe meglio non riservarlo e tenerlo del tutto al di fuori del range. 

Per fare un esempio: DHCP range 192.168.1.100 - 192.168.1.200, router sull'1, stampante sul 2, telecamera sul 3 e così via.

***

