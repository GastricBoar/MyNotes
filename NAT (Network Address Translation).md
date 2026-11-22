---
date: 2024-12-11-10-53
tags:
  - informatica
  - pubblico
---
# NAT (Network Address Translation)
---
Una tecnologia di rete che modifica e traduce indirizzi IP mentre transitano attraverso un dispositivo di rete.

### Tipi di NAT
Un paio di scopi per il quale viene utilizzato NAT.

### SNAT (Source NAT) o Masquerading
NAT in uscita, permette a più dispositivi con indirizzi IP privati di accedere a reti esterne condividendo un unico indirizzo IP pubblico. Per fare un esempio: il tuo cellulare a casa (192.168.1.37) esce su Internet tramite indirizzo pubblico (82.90.35.32).

### DNAT (Destination NAT) o Port Forwarding
NAT in entrata, permette a utenti esterni di raggiungere specifici servizi o server situati all'interno di una rete privata. Per fare un esempio: configuri il router in maniera che tutto il traffico che arriva sulla porta 25565 venga reindirizzato al tuo server di casa, per poterlo raggiungere dall'esterno.

### NAT infrastrutturale
Traduce l'intera struttura di indirizzi di una rete per collegarla a un'altra senza creare conflitti.

Per fare un esempio:

- Due aziende si fondono ed entrambe usano la stessa rete `192.168.1.x`, e magari hanno entrambe un host su `192.168.1.50`
  
- Se invii un pacchetto al `192.168.1.50` che si trova dentro la LAN dell'altra azienda, la tua rete cercherà quel computer dentro la LAN locale, creando un errore di conflitto
  
- Ri-assegnare tutti gli indirizzi IP sarebbe tedioso
  
- Configuri quindi il router per trasformare virtualmente la rete dell'altra azienda in `10.200.1.x`
  
- Quando invii il pacchetto a `10.200.1.50`, il router traduce al volo l'indirizzo e lo consegna al computer corretto dall'altra parte.

### NAT Traversal
Come dicevamo, il NAT blocca le connessioni in ingresso verso i dispositivi della rete locale. Questo significa che un computer esterno non può iniziare una connessione diretta verso il tuo PC senza configurazioni aggiuntive come il port forwarding.

Qui il NAT Traversal è un insieme di tecniche e protocolli ti consente di superare questa limitazione; permette la comunicazione diretta (P2P) o facilitata tra dispositivi nascosti dietro NAT.

In pratica:

- I due dispositivi contattano un server intermedio con IP pubblico per scoprire il proprio indirizzo pubblico e aprire un foro (hole punching) nei rispettivi NAT.

- Il server di mezzo aiuta i due dispositivi a scambiarsi queste informazioni per stabilire una connessione diretta tra loro (tramite protocolli come STUN o UPnP).

- Dovesse il NAT essere troppo rigido per instaurare una connessione, il server intermedio agisce da ponte (relay) inoltrando tutto il traffico tra i due dispositivi (tramite protocolli come TURN).

Un esempio di questa cosa è Rustdesk.

---