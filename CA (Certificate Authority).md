---
date: 2026-08-24
tags:
  - informatica
  - pubblico

---
# CA (Certificate Authority)
---
Autorità che emette e firma certificati digitali, permettendo ai client di verificare l'associazione tra un'identità, come un dominio, e una chiave pubblica.

### Chi sono?
Le CA possono essere aziende o organizzazioni; tra le più conosciute ci sono Let's Encrypt, DigiCert, Sectigo e Google Trust Services.

Esistono CA gratuite e a pagamento. Per un normale sito web, una CA gratuita come Let's Encrypt è generalmente sufficiente.

### Chi certifica le CA?
Le CA emettono i certificati digitali, è come prendere una persona fidata e dirle "garantisci tu per questa chiave?". A questo punto però chi garantisce per la persona fidata? chi controlla i controllori?

Questo giro si chiama catena di fiducia, e dentro ci trovi più livelli di fiducia: 

- **Le CA intermedie:** emette il certificato per `doggos.com`, ha a sua volta un certificato digitale, rilasciato e firmato dalla Root CA al livello superiore.
  
- **Le Root CA:** sta in cima alla piramide e firma il proprio certificato da sola.

A garantire per le Root CA ci sono i produttori di sistemi operativi e browser (Microsoft, Google, Apple, Mozilla etc.) che eseguono audit di sicurezza e legali rigidissimi. Se la Root CA supera i controlli, la sua chiave pubblica viene inserita direttamente nel Trust Store dei dispositivi distribuiti in tutto il mondo.

### Cosa è il Trust Store?
È un archivio integrato a sistema operativo o browser, contiene l'elenco di tutte le CA radice considerate ufficialmente affidabili, e le loro relative chiavi pubbliche. È già preinstallato, e viene mantenuto nel tempo tramite aggiornamenti di sistema.

Se un certificato proviene da una CA presente nel Trust Store, il client si fida della connessione; in caso contrario, ti mostra l'avviso di protezione (es. "La connessione non è privata"_).

---
[[Certificato digitale]]  
[[TLS (Transport Layer Security)]]
