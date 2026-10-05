---
date: 2026-07-30
tags:
  - informatica
  - pubblico

---
# CIFS (Common Internet File System)
---
Anche chiamato SMBv1, è un protocollo di rete di livello applicativo progettato per consentire la condivisione di file, cartelle e stampanti all'interno di una rete locale (LAN). Permette a un client di accedere, leggere, scrivere e gestire file e cartelle presenti su un altro dispositivo all'interno della stessa rete, come se quei file si trovassero sul proprio hard disk locale.

### La storia
La condivisione file in ambiente Microsoft parte nel 1983, quando IBM crea [[SMB (Server Message Block)]], un protocollo pensato per reti locali.

Nel 1996, con l'esplosione di Internet, Microsoft riprende SMB e lo aggiorna per farlo funzionare su WAN. Lo chiama CIFS, nel tentativo di trasformarlo in uno standard di rete aperto. A partire dal 2006 verrà anche chiamato SMBv1.

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

---
