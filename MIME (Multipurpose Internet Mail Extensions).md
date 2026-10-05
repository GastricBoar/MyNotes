---
date: 2026-08-29
tags:
  - informatica
  - pubblico

---
# MIME (Multipurpose Internet Mail Extensions)
---
Standard che estende il formato delle email per permettere di trasmettere contenuti diversi dal semplice testo ASCII, come immagini, documenti, audio e altri file.

### Il contesto
Le email erano originariamente progettate per trasportare solo testo semplice. Con il tempo si è reso necessario poter inviare anche immagini, documenti, audio e altri tipi di contenuto.

Il problema è che il formato originale delle email non aveva un modo standard per rappresentare questi contenuti: se volevi allegare una foto non esisteva un meccanismo che dicesse al programma di posta "questo è un file JPEG e lo devi mostrare come immagine".

### Come funziona?
Qui arriva MIME, che introduce un modo standard per strutturare e descrivere questi contenuti all'interno di un'email.

Per esempio:

- Vuoi inviare una foto a un amico.
  
- MIME indica che quella parte dell'email contiene un'immagine JPEG, lo fa inserendo un header `Content-Type: image/jpeg`.
  
- Una foto è però composta da dati binari (come `10101100`), e il sistema e-mail originale era pensato per trasformare testo, non sequenze arbitrarie di byte.
  
- Il client di posta allora prende questa sequenza e la rappresenta usando caratteri di testo, secondo codifica Base64. Allo stesso tempo, MIME inserisce un altro header che dice `Content-Transfer-Encoding: base64`.
  
- I dati vengono trasmessi come testo.
  
- Il client di posta del destinatario legge le informazioni MIME.
  
- Riconosce che i dati sono Base64 e li decodifica, ottenendo nuovamente i dati binari originali della foto.
  
- A questo punto può interpretarli come JPEG e mostrare l'immagine.
  
MIME descrive tramite header anche il formato di altri contenuti come HTML, e per gli allegati permette di specificare informazioni come il nome del file e il modo in cui il contenuto deve essere trattato. Non è inoltre limitato alle email: il formato e gli header MIME sono utilizzati anche in altri protocolli e applicazioni Internet, tra cui HTTP.

---
[[SMTP (Simple Mail Transfer Protocol)]]
[[IMAP (Internet Message Access Protocol)]]
[[POP (Post Office Protocol)]]
