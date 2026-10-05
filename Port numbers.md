---
date: 2024-12-27
tags:
  - informatica
  - pubblico

---
# Port numbers
---
I numeri di porta sono degli identificatori numerici utilizzati all'interno di protocolli di rete: se l'[[Indirizzo IP (Internet Protocol)]] identifica il dispositivo da raggiungere, il numero di porta identifica l'applicazione specifica all'interno di quel dispositivo.

Le porte esistono perchè i nostri dispositivi hanno bisogno di accedere contemporaneamente a diverse risorse su rete; per esempio, nello stesso momento il mio PC potrebbe voler accedere a un sito web, a un gioco su Steam, a una canzone su Spotify, a una stampante e così via.

I numeri di porta aiutano i pacchetti a essere indirizzati, nell'immagine giù vedi che i blocchi in verde indicano la porta dal quale arriva la richiesta e la porta al quale invece deve arrivare:

![Pasted image 20241229232644.png](Utilities/Media/Pasted%20image%2020241229232644.png)

### Categorie dei numeri di porta
I numeri di porta vanno da 0 a 65.535, ma sono suddivisi in tre categorie:

- **Porte well-known (0 a 1023):** porte fisse e riservate a servizi standard, per fare un esempio la porta riservata al protocollo HTTPS sarà sempre associata al numero di porta 443; una porta well-known deve essere registrata dalla IANA (Internet Assigned Numbers Authority) come tale, è importante abbiano un numero dedicato e non vadano in conflitto con altro.

- **Porte registrate (1024 a 49.151):** sono porte assegnate ad applicazioni specifiche che ne hanno richiesto una registrazione presso la IANA; per esempio, la porta 27015 viene utilizzata da Steam. A differenza delle porte well-known, possono essere utilizzate anche da altre applicazioni, ma la IANA suggerisce di usarle per le specifiche applicazioni registrate.

- **Porte dinamiche/effimere (49.152 a 65.535):** sono le porte utilizzate temporaneamente dalle applicazioni per le connessioni di tutti i giorni.

Qui c'è una tabella di numeri di porta well-known che è meglio ricordare:

|Porta|Protocollo|Uso/Descrizione|Tipo|
|--:|---|---|---|
|20|FTP (dati)|Trasferimento file (canale dati)|TCP|
|21|FTP (controllo)|Trasferimento file (gestione connessione)|TCP|
|22|SSH|Accesso remoto sicuro|TCP|
|23|Telnet|Accesso remoto (non sicuro)|TCP|
|25|SMTP|Invio email|TCP|
|53|DNS|Risoluzione dei nomi in indirizzi IP|TCP/UDP|
|67|DHCP (server)|Assegnazione dinamica degli indirizzi IP|UDP|
|68|DHCP (client)|Ricezione dell'assegnazione IP|UDP|
|69|TFTP|Trasferimento file semplice|UDP|
|80|HTTP|Navigazione web (non sicura)|TCP|
|110|POP3|Ricezione email|TCP|
|143|IMAP|Accesso email su server|TCP|
|161|SNMP|Monitoraggio e gestione della rete|UDP|
|162|SNMP Trap|Notifiche SNMP|UDP|
|389|LDAP|Accesso a directory di rete|TCP/UDP|
|443|HTTPS|Navigazione web sicura|TCP|
|445|SMB|Condivisione file e risorse in rete|TCP|
|3389|RDP|Desktop remoto|TCP|
### Come verifico a quale porte son attualmente connesso?
Puoi aprire il pannello di monitoraggio risorse, selezionare la scheda "rete" e poi espandere la sezione che riguarda le connessioni TCP:

![Pasted image 20241229232010.png](Utilities/Media/Pasted%20image%2020241229232010.png)

---
