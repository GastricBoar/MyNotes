---
date: 2026-08-20
tags:
  - informatica
  - pubblico

---
# HTTP (HyperText Transfer Protocol)
---
Protocollo di comunicazione utilizzato per trasferire risorse, come pagine web, immagini e file, tra client e server attraverso una rete.

### Come funziona?
È basato su un'architettura client-server: il client invia una richiesta HTTP al server e il server restituisce una risposta HTTP. Per fare un esempio:

- Inserisci `http://www.neverssl.com` nel browser.
- Il browser, che è il client, invia una richiesta HTTP al server dietro il sito.
- Il server elabora la richiesta e restituisce una risposta contenente le risorse richieste, come il codice HTML della pagina.
- Il browser interpreta la risposta e visualizza la pagina web.

Utilizza di default la porta TCP 80.

### I metodi HTTP
Indicano il tipo di operazione che il client vuole eseguire su una risorsa:

- **GET:** richiede una risorsa al server (es. una pagina web).
- **POST:** chiede al server di creare una nuova risorsa, lasciando al server la scelta dell'identificativo.
- **PUT:** chiede al server di creare o sostituire una risorsa a un indirizzo specifico.
- **DELETE:** chiede al server di eliminare una risorsa specifica.

La differenza tra POST e PUT può essere sottile da intendere, quindi faccio un esempio:

- Immagina di avere un gestionale con sopra dei prodotti, vuoi aggiungere un nuovo prodotto.
  
- Con POST invii i dati a `/prodotti`, lasciando al server il compito di assegnargli un identificativo, `847`.
  
- Viene creato `/prodotti/847` contenente dati:
  
```
  {
  "nome": "Tastiera",
  "prezzo": 80
  }
```

- Con PUT puoi sia creare che aggiornare un prodotto in maniera specifica. 
  
- Potresti chiedere al server di creare la risorsa `960` specificando tu stesso l'identificativo.
  
- Potresti chiedere al server di modificare i dati della risorsa `847`.

### Le caratteristiche
Un paio:

- **È un protocollo stateless**, ogni richiesta viene trattata indipendentemente dalle precedenti; per mantenere continuità di informazioni tra più richieste vengono utilizzati meccanismi come cookie e sessioni.
  
- **HTTP non è cifrato:** i dati vengono trasmessi in chiaro, al contrario di HTTPS, che aggiunge crittografia tramite [[TLS (Transport Layer Security)]].

### Codici di stato
Codici con il quale il server comunica l'esito della richiesta:

- **200 OK:** richiesta completata correttamente.
- **301 Moved Permanently:** la risorsa è stata spostata permanentemente.
- **400 Bad Request:** richiesta non valida.
- **401 Unauthorized:** autenticazione richiesta.
- **403 Forbidden:** accesso negato.
- **404 Not Found:** risorsa non trovata.
- **500 Internal Server Error:** errore interno del server.

---
