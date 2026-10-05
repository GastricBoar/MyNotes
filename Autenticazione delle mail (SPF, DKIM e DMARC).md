---
date: 2025-01-08
tags:
  - informatica
  - pubblico

---
# Autenticazione delle mail (SPF, DKIM e DMARC)
***
Tre tecnologie interne al [[DNS (Domain Name Server)]] utilizzate per autenticare le e-mail, verificano l'identità del mittente e si assicurano che e-mail fraudolente non raggiungano i destinatari. Vengono spesso configurate a partire dal pannello di amministrazione DNS stesso.

#### **SPF (Sender Policy Framework)**
Permette al proprietario di un dominio di specificare quali server siano autorizzati a inviare email per conto di quel dominio.

Nel pratico assomiglia a questo:

```
v=spf1 include:_spf.google.com -all
```

Questo è un record TXT ([[Record DNS]]) di SPF, dirà al server di posta (tipo google.com) del destinatario "se ti arriva un messaggio da qualcuno che dice di essere me, ricorda che l'indirizzo IP del server mittente deve essere questo; se non è questo, non sono io."

- `v=spf1` indica che è un record SPF.
- `include:_spf.google.com`: autorizza i server di Google a inviare email.
- `-all`: indica che qualsiasi altro server non autorizzato deve essere rifiutato.
#### **DKIM (DomainKeys Identified Mail)**
Permette al proprietario di un dominio di "firmare" le proprie mail, questo permette al destinatario di far due cose: verificare l'identità del mittente (come fa SPF) e verificare che il messaggio non sia stato manipolato durante il trasporto. 

Nel pratico la cosa viene svolta tramite crittografia:

- Lato DNS viene definita una chiave pubblica.
- Il mittente utilizza invece una chiave privata per firmare le proprie mail.
- Il server del destinatario verifica la firma data dalla chiave privata, utilizzando la chiave pubblica.

È come dicesse "questa è la mia firma, se non ti torna allora non sono stato io a inviare questa mail oppure non è quello che ho scritto originariamente".

```
default._domainkey.miosito.com    TXT    "v=DKIM1; k=rsa; p=MIIBIjANBg..."
```

In questo esempio:

- `default._domainkey.miosito.com` è il nome della chiave pubblica.
- `TXT` è il tipo di record.
 - `v=DKIM1`: indica che è un record DKIM.
- `k=rsa`: Indica il tipo di crittografia/chiave.
- `p=...`: Contiene il valore della chiave pubblica.

#### **DMARC (Domain-based Message Authentication, Reporting, and Conformance)**
Un livello aggiuntivo di protezione su SPF e DKIM, permette al proprietario del dominio di indicare cosa bisogna fare con quella mail nel caso in cui i controlli SPF e DKIM siano stati falliti. È come dicesse "se hai ricevuto una mail contraffatta che dice di essere me, ecco cosa devi farci".

In genere sono istruzioni come:

- **none**: non far nulla, invia un report e basta.
- **quarantine:** invia la mail in spam.
- **reject:** rifiuta la mail.

Come al solito, si tratta di un record TXT:

```
_dmarc.miosito.com    TXT    "v=DMARC1; p=reject; rua=mailto:dmarc-reports@miosito.com"
```

- `v=DMARC1`: specifica la versione.
- `p=reject`: richiede di rifiutare le email non conformi.
- `rua=mailto:...`: indica l'indirizzo per inviare i report DMARC.
***

