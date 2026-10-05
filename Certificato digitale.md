---
date: 2026-08-22
tags:
  - informatica
  - pubblico

---
# Certificato digitale
---
Documento digitale utilizzato per associare un'identità a una chiave pubblica, permettendo a un client di verificarne l'autenticità.

### Il contesto
Quando un client si connette a un server, deve poter verificare con chi sta realmente comunicando, evitando che un attaccante possa spacciarsi per il server legittimo.

Per fare un esempio:

- Hai un sito web chiamato `doggos.com` sul tuo server, e decidi di utilizzare HTTPS.
- Configurare HTTPS ti richiede la generazione di due chiavi crittografiche: una privata e una pubblica.
- La chiave privata resta sul server, la chiave pubblica può essere condivisa.
- A questo punto hai bisogno di un certificato digitale.
- I certificati digitali vengono emessi dalle CA.
- Proprio come il tuo server, anche le CA possiedono una propria coppia di chiavi: una chiave privata che usa per firmare i certificati che emette, e una chiave pubblica che serve ai client per verificare quelle firme.

### Chi certifica le CA?
Le CA emettono i certificati digitali, è come prendere una persona fidata e dirle "garantisci tu per questa chiave?". A questo punto però chi garantisce per la persona fidata? chi controlla i controllori?

Questo giro si chiama catena di fiducia, e dentro ci trovi più livelli di fiducia: 

- **Le CA intermedie:** emette il certificato per `doggos.com`, ha a sua volta un certificato digitale, rilasciato e firmato dalla Root CA al livello superiore.
  
- **Le Root CA:** sta in cima alla piramide e firma il proprio certificato da sola.

A garantire per le Root CA ci sono i produttori di sistemi operativi e browser (Microsoft, Google, Apple, Mozilla etc.) che eseguono audit di sicurezza e legali rigidissimi. Se la Root CA supera i controlli, la sua chiave pubblica viene inserita direttamente nel Trust Store dei dispositivi distribuiti in tutto il mondo.

### Cosa è il Trust Store?
È un archivio integrato a sistema operativo o browser, contiene l'elenco di tutte le CA radice considerate ufficialmente affidabili, e le loro relative chiavi pubbliche. È già preinstallato, e viene mantenuto nel tempo tramite aggiornamenti di sistema.

Se un certificato proviene da una CA presente nel Trust Store, il client si fida della connessione; in caso contrario, ti mostra l'avviso di protezione (es. "La connessione non è privata"_).

### Come viene rilasciato un certificato?
I certificati vengono emessi e firmati digitalmente da una CA (Certificate Authority). Per tornare all'esempio di prima:

- Scegli una CA a tuo piacimento, che sia gratuita o a pagamento.
  
- La tua CA chiede di dimostrare che sia davvero tu a controllare il dominio `doggos.com`

- Ti dice "crea il file `/.well-known/acme-challenge/abc123` e scrivici dentro `xyz789`"
- La CA raggiunge il tuo sito e verifica il file contenga il valore richiesto.
  
Questo verifica la tua identità, a questo punto la CA deve creare il certificato digitale:

- Prende le informazioni (dominio, la tua chiave pubblica, scadenze).
  
- Ne calcola un impronta digitale (hash) e la cifra con la propria chiave privata; quella cifra è la firma digitale della CA.
  
- Fatto, certificato digitale emesso; attesta ufficialmente che la chiave pubblica generata dal tuo server è associata al dominio `doggos.com`
  
### Cosa contiene un certificato?
Il certificato è stato emesso, i tuoi sforzi sono stati ripagati. I certificati possono contenere tante informazioni, ma parlando del tuo caso specifico ti è utile perchè contiene:

- Nome del dominio o dell'entità a cui è stato rilasciato (es. `doggos.com`)
- Chiave pubblica generata dal server
- CA che lo ha emesso (es. Sectigo)
- Periodo di validità.
- Firma digitale della CA.

Questo attestato dice "La chiave pubblica X generata dal server appartiene a `doggos.com` fino al 24 agosto 2030, e lo certifico io, Sectigo."

### Come verificano il certificato i client?
Hai il tuo bel certificato scintillante, ma l'ultimo attore della catena è il client che, tramite browser o sistema operativo, deve verificare tre cose: che il certificato sia autentico, che non sia stato alterato durante il trasporto, e che la chiave pubblica ricevuta appartenga davvero al dominio indicato. 

Proseguendo con l'esempio:

- L'utente finale visita `doggos.com` a partire dal proprio client.
  
- Il server che hosta `doggos.com` risponde inviando al browser dell'utente la propria chiave pubblica e il certificato digitale firmato da Sectigo.
  
- Il browser legge il certificato e vede che è stato firmato da Sectigo. Deve verificare che il certificato sia davvero stato creato da Sectigo, e che non sia stato manomesso durante il tragitto.

- Cerca quindi la chiave pubblica di Sectigo all'interno del proprio Trust Store.
  
- Usando la chiave pubblica di Sectigo, il browser decifra la firma digitale presente sul certificato: se la firma torna, ha la certezza matematica che il certificato è autentico e non è stato alterato da nessuno. Sectigo aveva inoltre impacchettato e firmato assieme la chiave pubblica del server con il nome dominio `doggos.com` associato, quindi anche la terza condizione è verificata.
  
- Per finire, il browser controlla le date di validità e che il nome sul certificato corrisponda esattamente a `doggos.com`. Se tutto coincide, la connessione diventa sicura.

---
[[CA (Certificate Authority)]]

[[TLS (Transport Layer Security)]]

[[HTTPS (HyperText Transfer Protocol Secure)]]