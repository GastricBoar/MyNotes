---
date: 2024-12-26
tags:
  - informatica
  - pubblico

---
# DHCP (Dynamic Host Configuration Protocol)
---
Protocollo di rete che assegna automaticamente indirizzo IP e altre configurazioni a un dispositivo in rete.

### Il contesto
Un dispositivo ha bisogno di alcune informazioni per poter comunicare con gli altri dispositivi in rete o raggiungere Internet:

- **Indirizzo IP:** identifica il dispositivo all'interno della rete.

- **Subnet mask:** definisce quale parte dell'indirizzo IP identifica la rete e quale identifica il dispositivo, es. se hai IP `192.168.1.100` e subnet mask `255.255.255.0`, la rete è `192.168.1.0` e l'indirizzo del dispositivo è `192.168.1.100`.

- **Default gateway:** indica a quale router inoltrare il traffico destinato a reti diverse da quella locale.

- **DNS server:** traduce i nomi di dominio (come `google.com`) in rispettivi indirizzi IP.

Queste informazioni puoi configurarle manualmente sul tuo dispositivo; tu penserai "ma io non ricordo mica di aver assegnato un indirizzo IP a nessuno dei miei dispositiv-" ma io gnognegnegne- grande minchione, non lo hai mai dovuto assegnare perchè qualcos'altro lo ha fatto per te, e quel qualcosa si chiama "server DHCP".

### Come funziona?
Un dispositivo svolge il ruolo DHCP, generalmente si tratta di un router o un server. Il dispositivo che ricopre quest ruolo mette a disposizione una configurazione di rete e la assegna ai dispositivi (i client DHCP) che ne fanno richiesta.

Nel pratico avviene in quattro passaggi, conosciuti con l'acronimo DORA:

1. **Discover:** il client cerca un server DHCP in rete.

2. **Offer:** il server risponde proponendo una configurazione di rete.

3. **Request:** il dispositivo richiede formalmente la configurazione proposta.

4. **Acknowledge:** il server conferma l'assegnazione e concede al dispositivo l'utilizzo della configurazione per un determinato periodo di tempo, chiamato lease time.

Immagina se questo meccanismo non esistesse: per collegarti al Wi-Fi della biblioteca dovresti presentarti davanti alla biblotecaria e chiederle "mi ferve fapere il mio indirizzo IP, la mia fubnet mafk e un default gateway".

Se vuoi verificare il server DHCP al quale sei collegato apri il CMD, scrivici dentro `ipconfig /all` e scorri in basso alla scheda di rete che stai utilizzando; lì trovi l'indirizzo IP del server DHCP al quale sei collegato:

<img src="Utilities/Media/Pasted%20image%2020241226004521.png" alt="Pasted image 20241226004521.png" width="577">

Un server DHCP lo configuri con una serie di parametri:

- **Il DHCP range:** l'intervallo di indirizzi assegnabili dal server, es. assegna ai dispositivi indirizzi compresi nel range 192.168.1.100 - 192.168.1.200.

- **Il DHCP address:** specifica a quale rete applicare le impostazioni DHCP; un server DHCP potrebbe gestire più reti con parametri differenti, es. hai una rete 192.168.1.0/24 per i computer e una rete 192.168.2.0/24 per i dispositivi IoT, assegnando a ciascuna un gateway e un DNS differenti.

- **Il DHCP lease:** il periodo di tempo entro il quale un indirizzo assegnato resta valido per un certo client. Prima della scadenza, quel dispositivo tenta di rinnovare il lease; se non ci riesce, l'indirizzo torna al pool diventando disponibile per gli altri dispositivi in rete.

- **Le DHCP reservations:** assegni permanentemente un indirizzo IP a un certo client, nonostante quell'indirizzo faccia parte del pool di indirizzi dinamici. È utile assegnare un indirizzo statico a dispositivi come stampanti, server e telecamere; in molti casi però non ha senso riservare un indirizzo all'interno del DHCP range, sarebbe meglio non riservarlo e tenerlo del tutto al di fuori del range, es. DHCP range 192.168.1.100 - 192.168.1.200, router sull'1, stampante sul 2, telecamera sul 3 e così via.

Se il tuo server DHCP va giù, i client prendono un indirizzo IP privato tramite APIPA.

***
[[APIPA (Automatic Private IP Addressing)]]
[[LAN (Local Area Network)]]
[[Risolvere problemi legati al server DHCP]]
