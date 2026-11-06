---
date: 2026-08-20
tags:
  - informatica
  - pubblico

---
# SSH (Secure Shell)
---
Protocollo di rete che permette di stabilire una connessione remota sicura con un altro sistema. 

### Il contesto
Nasce nel 1995 con l'obbiettivo di sostituire protocolli di accesso remoto come Telnet e rlogin; il problema di questi protocolli è che trasmettevano in chiaro informazioni sensibili come credenziali, comandi digitati, output dei comandi e altri dati.

SSH ti permette di accedere a sistemi remoti tramite terminale, ma ci aggiunge cifratura e autenticazione sicura; è importante per contrastare sniffing e attacchi Man-in-the-Middle.

### Come funziona?
La connessione avviene così: Il client SSH contatta il server SSH, sulla porta TCP 22 (di default). Da lì, client e server devono accordarsi su un paio di cose prima di poter comunicare; tutta questa fase che vedremo giù si chiama handshake.

#### Negoziare gli algoritmi
Abbiamo detto che la comunicazione tramite SSH è cifrata e verificata, ma in che modo? client e server potrebbero supportare algoritmi crittografici diversi, quindi cominciano comunicandosi reciprocamente le proprie liste di algoritmi supporati. Diverse attività possono richiedere algoritmi diversi, anche all'interno della stessa fase.

Confrontando le liste, individuano gli algoritmi compatibili per fare quello che gli serve fare; ma cosa è che gli serve fare?

#### Stabilire un segreto condiviso (key exchange)
Per poter comunicare in maniera cifrata, client e server devono disporre di una chiave segreta con il quale poter decifrare il messaggio ricevuto; come possono ricavare questa chiave senza trasmetterla direttamente sulla rete, dove potrebbe essere intercettata?

Utilizzano un algoritmo di scambio delle chiavi (key exchange), come Diffie-Hellman o Curve25519. Questi algoritmi permettono a client e server di scambiarsi alcuni valori pubblici e, attraverso operazioni matematiche, calcolare autonomamente un segreto condiviso, senza trasmetterlo direttamente sulla rete.

Questo segreto condiviso viene poi elaborato da una funzione di derivazione delle chiavi, che genera le chiavi crittografiche effettivamente utilizzate per cifrare e decifrare i dati della sessione SSH.

#### Cifrare la comunicazione
Client e server adesso hanno ottenuto le chiavi della sessione, ma come le usano per proteggere i dati che si scambieranno? 

Qui serve un algoritmo di cifratura simmetrica; si chiama "cifratura simmetrica" perchè utilizzi la stessa chiave segreta per cifrare e decifrare un messaggio. È diversa dalla cifratura asimmetrica, dove hai una coppia di chiavi diverse (privata e pubblica).

Ci sono un paio di algoritmi di cifratura simmetrica, per esempio AES o ChaCha20, e trasformano i dati originali in dati cifrati tramite la chiave segreta che abbiamo ricavato prima.

#### Verificare l'identità del server (host key)
Abbiamo stabilito un segreto condiviso e possiamo cifrare la comunicazione, ma come facciamo a sapere che il server con cui stiamo comunicando è davvero quello a cui volevamo collegarci, e non un impostore?

Serve una host key: una coppia di chiavi crittografiche (pubblica e privata) generate dal server; la chiave privata rimane sul server per poter firmare alcuni dati dello scambio, quella pubblica viene comunicata al client affinchè possa verificare la firma ricevuta.

Il client riceve la chiave pubblica del server, ed è una chiave molto lunga; invece che mostrarti tutta la chiave, usa una funzione matematica (hash) per calcolarne un valore più breve e facilmente confrontabile: l'impronta digitale (fingerprint).

Alla prima connessione con quel server, il client ti mostra a schermo l'impronta digitale calcolata, chiedendoti se considerarla affidabile, tipo così:

```
The authenticity of host '192.168.1.100' can't be established.
ED25519 key fingerprint is SHA256:AbCdEf123456...
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

Se accetti, salva quella chiave pubblica nel file `~/.ssh/known_hosts`. Nelle connessioni successive, il client confronterà la chiave pubblica comunicata con quella registrata nel file `known_hosts`, e se cambia segnala un possibile problema.

Attenzione: l'impronta digitale da sola non dimostra che il server sia autentico; alla prima connessione dovresti confrontarla con una fingerprint ottenuta da una fonte indipendente e affidabile, se vogliamo essere più sicuri.

#### Verificare l'identità dell'utente (host key)
Abbiamo verificato che il server sia quello corretto e stabilito una comunicazione sicura. Ma il server deve ancora capire chi è l'utente e se abbia il diritto di accedere.

L'autenticazione avviene tramite password oppure tramite coppia di chiavi crittografiche, offrendo un livello di sicurezza ancora più elevato. Funziona così:

- Crei una coppia di chiavi sul tuo PC locale con il comando `ssh-keygen`, questo genera una chiave privata e una chiave pubblica.
  
- La chiave privata resta segreta, la tieni sul tuo PC.
  
- La chiave pubblica la copi sul server remoto, generalmente dentro `~/.ssh/authorized_keys` usando il comando `ssh-copy-id admin@192.168.1.1`.
  
- Da quel momento in poi, connettersi in ssh non richiederà alcuna password, perchè il tuo PC ti autentica tramite controllo crittografico.

#### Connettersi alla sessione remota
Oltre la connessione tramite password, puoi usare il comando `ssh -i ~/.ssh/id_ed25519 paolo@192.168.1.100` per autenticarti tramite chiave privata.

Se vuoi un comando ancora più elegante, puoi creare un alias:

- Crea una directory `.ssh` nella tua home, se non esiste già.
  
- All'interno crea un file chiamato `config` e mettici dentro:

```
      Host linux-upskill-challenge
        HostName indirizzo-ip-del-server
        User tuo-username
        Port 22
```
   
- A questo punto puoi collegarti al server semplicemente digitando  `ssh linux-upskill-challenge`

### Funzionalità aggiuntive
Oltre all'accesso alla riga di comando, SSH ti offre anche altre funzionalità:

- **Trasferimento file sicuro:** supporta i protocolli SFTP e SCP per copiare file in modo cifrato tra due host.

- **SSH tunneling:** ti permette di incapsulare il traffico di altre applicazioni non sicure all'interno del canale cifrato di SSH.

---
[[ssh (comando)]]