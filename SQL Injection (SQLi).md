---
date: 2026-09-01
tags:
  - informatica
  - pubblico

---
# SQL Injection (SQLi)
---
Attacco informatico in cui l'attaccante inserisce codice SQL malevolo all'interno dell'input fornito a un'applicazione, cercando di manipolare la query SQL che l'applicazione esegue sul database.

### Come funziona?

- Dietro molte applicazioni e siti web ci sta un database che, tra le altre cose, memorizza dati sensibili come utenti, password e transazioni.
  
- L'applicazione comunica con il database inviando query SQL generate a partire dall'utente; per fare un esempio, la tua banca ha un form di login che ti richiede di inserire nome utente e password.
  
- Dietro quel campo ci sta una query SQL che dice `SELECT * FROM utenti WHERE username = 'INPUT_UTENTE' AND password = 'INPUT_PASSWORD';`
  
- Solitamente lo riempiresti come `SELECT * FROM utenti WHERE username = 'mario' AND password = '1234';`
  
- Invece di inserire credenziali standard, potresti digitare una stringa che altera la sintassi della query originale, es. se nel campo input scrivi `admin' OR '1'='1` la query leggerà `SELECT * FROM utenti WHERE username = 'admin' OR '1'='1' AND password = '1234';`

- In SQL l'operatore `AND` ha priorità più alta rispetto all'operatore `OR`, quindi viene interpretata come `SELECT * FROM utenti WHERE username = 'admin' OR ('1'='1' AND password = '1234');`

- Partendo dalla parentesi, SQL chiede "1 è uguale a 1, e allo stesso tempo la password è 1234?"; la prima condizione è vera, la seconda dipende dalla password dell'utente, quindi il risultato della parentesi sarà vero solo se la password è 1234.

- A questo punto SQL valuta la parte `username = 'admin' OR (...)`: la prima condizione è vera perché hai inserito lo username è `admin`. Di conseguenza, non importa se la parentesi successiva sia vera o falsa: `VERO OR FALSO` è comunque `VERO`.

- La query ti restituisce l'utente `admin`, indipendentemente dal fatto che la sua password sia `1234`.

Ti sei quindi autenticato all'utente admin senza conoscerne la password, ma di esempi ce ne sono molti altri, a seconda dell'account utilizzato dall'applicazione, una SQL injection può permettere di 

- **Leggere dati:** ottenere informazioni presenti nel database.
- **Modificare dati:** alterare informazioni esistenti.
- **Cancellare dati:** eliminare informazioni dal database.
- **Bypassare l'autenticazione:** manipolare una query di login per ottenere accesso senza conoscere le credenziali corrette.

### Tecniche di SQL Injection
Le SQL Injection seguono diverse tecniche in base al modo in cui l'attaccante inserisce l'input e riesce a ottenere informazioni dal database; ne elenco cinque tra le più comuni, ma ce ne sono molte altre:

- **In-band SQL Injection:** l'attaccante inserisce codice SQL nel campo input dell'applicazione e riceve i risultati attraverso lo stesso canale; "in-band" è un'espressione che in informatica significa "comunicazione che utilizza lo stesso canale normalmente utilizzato per lo scambio di dati".
  
- **Error-based SQL Injection:** l'attaccante provoca intenzionalmente errori per ottenere informazioni sulla struttura o sui dati del database.
  
- **Blind SQL Injection:** l'attaccante utilizza condizioni booleane `vero` o `falso` per dedurre informazioni sul database.
  
- **Out-of-band SQL Injection:** l'attaccante forza il database a inviare informazioni attraverso un canale esterno, per esempio tramite richieste DNS o HTTP.
  
- **Time-based Blind SQL Injection:** variante della Blind SQL Injection, l'attaccante inserisce codice che provoca intenzionalmente un ritardo nella risposta e utilizza quel tempo di risposta del server per dedurre informazioni.
  
### Come si previene?
La difesa principale consiste nel separare i dati forniti dall'utente dal codice SQL, impedendo che l'input possa essere interpretato come istruzione.

- **Usa query parametrizzate (prepared statements):** i dati dell'utente vengono trattati come valori e non come codice SQL.
  
- **Valida gli input:** configura quindi condizioni per il quale i dati ricevuti debbano rispettare il formato atteso.
  
- **Limita i privilegi del database:** l'account utilizzato dall'applicazione dovrebbe avere solo i permessi necessari.
  
- **Non mostrare errori SQL dettagliati:** impedisce all'attaccante di ottenere informazioni sulla struttura del database.

---
[[Man-in-the-Middle (MitM)]]
[[Evil Twin]]
[[Insider Threat]]
