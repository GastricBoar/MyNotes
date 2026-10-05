---
date: 2026-07-30
tags:
  - informatica
  - pubblico

---
# SMB (Server Message Block)
---
Famiglia di protocolli di rete di livello applicativo progettata per consentire la condivisione di file, cartelle e stampanti all'interno di una rete locale (LAN). 

È oggi lo standard nativo dei sistemi Windows per consentire a un client di accedere, leggere, scrivere e gestire risorse presenti su un altro dispositivo di rete, come se si trovassero sul proprio disco locale.

### La storia
La condivisione file in ambiente Microsoft parte nel 1983, quando IBM crea SMB.

Nel 1996, con l'esplosione di Internet, Microsoft riprende SMB e lo aggiorna per farlo funzionare su WAN. Lo chiama [[CIFS (Common Internet File System)]], nel tentativo di trasformarlo in uno standard di rete aperto. A partire dal 2006 verrà anche chiamato SMBv1.

Con il tempo si rivela lento e insicuro per il web, Microsoft ne riscrive il codice da zero nel 2006, chiamandolo SMB v2, il che aggiudica al protocollo del 1996 il soprannome di SMBv1

Nel tempo arriveranno anche SMBv3 (del 2012) e rilasci a partire da lì.

### Come funziona?
All'interno della rete si occupa di diverse cose.

### Gestisce file e cartelle
Consente l'apertura, la lettura, la scrittura, la rinomina e l'eliminazione remota dei dati tra client e server. Allo stesso modo, impedisce a più utenti di sovrascrivere o modificare contemporaneamente lo stesso file aperto in rete.

Per fare un esempio:

- Vuoi aprire un PDF chiamato "Contratto.pdf" che si trova su un server di rete aziendale (\\SERVER-UFFICIO\Documenti).
  
- Quando fai doppio clic sul file, il tuo computer utilizza CIFS\SMBv1 per dire al server "L'utente Mario vuole aprire questo PDF".

- Assieme alla richiesta, invia le tue credenziali di rete al server, che le convalida comparandole alle sue tabelle di autorizzazione ACL. 
  
- Risponde "Permessi validi, ecco i blocchi di dati del file richiesto".

- CIFS scarica i dati in RAM temporaneamente, in modo da farti visualizzare il documento, e allo stesso tempo blocca il file su server, dichiarando alla rete che quel file è attualmente aperto da te.
  
### Gestisce servizi e stampanti
Gestisce il reindirizzamento delle code di stampa di rete e la comunicazione per i servizi remoti.

Per fare due esempi:

- Vuoi stampare un file, ma la stampante è collegata fisicamente al PC di un altro ufficio. Quando premi "Stampa", il tuo computer invia il documento tramite SMB al PC della reception, che lo inserisce nella propria coda e lo invia alla stampante fisica.
  
- Da amministratore cambi la password di un utente sul server aziendale dal tuo PC. Tramite SMB, il tuo computer invia l'ordine al sistema operativo del server, che esegue il comando e aggiorna la password nel suo database locale.

### E su Linux e MacOS?
MacOS utilizza una propria implementazione di SMBv2 e v3, è nativamente compatibile con sistemi Windows (es. smb://nome-server)

Linux utilizza [[Samba]], oppure cifs-utils a livello file system. Per comunicare tra dispositivi Unix invece utilizza [[NFS (Network File System)]], che è nativo, più leggero ed efficiente per quel tipo di utilizzo.

---
