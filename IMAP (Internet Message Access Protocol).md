---
date: 2025-03-03
tags:
  - informatica
  - pubblico

---
# IMAP (Internet Message Access Protocol)
---
Un [[Protocollo]] di comunicazione, permette a un client di raccogliere email da un server di posta. Quelle mail sono arrivate sul server di posta grazie al protocollo [[SMTP (Simple Mail Transfer Protocol)]].

Lavora sulla porta 993 nella sua versione con SSL, oppure su porta 143 nella sua versione non sicura.

A differenza del protocollo [[POP (Post Office Protocol)]], il protocollo IMAP legge le mail dal server di posta e le tiene sincronizzate tra diversi dispositivi; le può scaricare per tenerle in memoria locale, ma non le elimina dal server di posta come il POP (a meno che non venga specificata la cosa). 

I client che utilizzano questo protocollo offrono tante funzionalità diverse rispetto a un client che utilizza POP, parlo di cose come cartelle, archivi, e-mail eliminate, conferme di lettura e così via; questo è possibile proprio in virtù del fatto che le mail vengono archiviate su un server.

Un server IMAP (detto incoming) assomiglia a `imap.gmail.com`.

---
