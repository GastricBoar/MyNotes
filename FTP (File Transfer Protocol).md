---
date: 2026-08-25
tags:
  - informatica
  - pubblico

---
# FTP (File Transfer Protocol)
---
Protocollo di rete di livello applicativo utilizzato per il trasferimento di file tra client e server all'interno di una rete TCP/IP.

### Come funziona?
La cosa particolare di FTP è che, rispetto ad altri protocolli, utilizza due diversi canali (sono due connessioni TCP separate) per gestire la comunicazione:

- **Canale di controllo:** utilizzato per inviare comandi come login, navigazione tra cartelle, richieste di download/upload, abort, e per ricevere codici di risposta dal server. Rimane aperto per tutta la durata della sessione, su porta 21.

- **Canale dati:** utilizzato e aperto solo al momento del trasferimento effettivo di file, si chiude appena il trasferimento è completato. Viaggia di default su porta 20 TCP, oppure dinamica.

Dividere la comunicazione su due binari ti permette di evitare situazioni in cui un trasferimento di dati molto pesante occupi tutta la banda della connessione, bloccando l'invio di nuovi comandi.

Per fare un esempio:

- Stai scaricando un file da 10 GB
- Se la connessione fosse unica, il canale sarebbe completamente saturo dai dati in transito e il server non sentirebbe più i tuoi comandi (es. un abort) fino a download terminato.

### Modalità di connessione
Due diverse modalità per stabilire la connessione dati.

### Modalità passiva (PASV)
Qui è il client che si connette al server sia per i comandi sia per il trasferimento dati:

- Il client apre il canale di controllo sulla porta 21 e invia il comando `PASV` per segnalare al server che non può o non vuole ricevere connessioni in ingresso.

- Il server accetta la richiesta, riserva una propria porta effimera (es. 60123) e la comunica al client tramite il canale di controllo.

- Il client prende l'iniziativa e fa una seconda chiamata in uscita, collegandosi dalla propria porta locale verso la porta effimera comunicata dal server per aprire il canale dati.

È la modalità usata di default oggi, poiché supera nativamente i problemi di firewall e NAT lato client: le connessioni sono entrambe avviate dal client verso l'esterno, quindi i router domestici le lasciano passare senza bisogno di configurazioni speciali.

### Modalità attiva
Qui è il server che si connette al client per trasferire dati:

- Il client apre canale di controllo su porta 21, chiede al server di avviare una connessione dati presso una propria porta effimera (es. 50321).
  
- Il server prende iniziativa e fa una chiamata in uscita, dalla propria porta 20 verso la porta effimera dichiarata dal client prima.

È una modalità storica, pensata per quando non esistevano firewall locali o router con NAT. Non si usa quasi più al giorno d'oggi, perchè il router vedrebbe una connessione dati che dall'esterno punta a una porta casuale; per sicurezza la bloccherebbe, a meno che non si configuri port triggering lato router, con il quale dici "sto per fare una chiamata FTP su porta 21 verso l'esterno, se vedi tornare una chiamata dal server FTP non bloccarla, lascia passare la risposta".

### Sicurezza e limiti
Il protocollo FTP nativo non è sicuro: trasmette credenziali (username/password) e contenuti dei file completamente in chiaro.

Per ovviare ai limiti di sicurezza del protocollo originario si usano:

- **FTPS (FTP over SSL/TLS):** protocollo FTP incapsulato all'interno di un canale crittografato SSL/TLS; mantiene la struttura a due canali.

- **SFTP (SSH File Transfer Protocol):** questo non è FTP! è un protocollo completamente diverso, funziona tramite SSH sulla porta TCP 22. Utilizza un singolo canale sicuro per comandi e dati, è oggi lo standard di fatto per il trasferimento file sicuro.

---