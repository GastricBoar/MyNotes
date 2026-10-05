---
date: 2026-09-07
tags:
  - informatica
  - pubblico

---
# BEC (Business Email Compromise)
---
Tipo di truffa informatica in cui un malintenzionato si inserisce segretamente in comunicazioni aziendali (spesso impersonando un dirigente o un fornitore) per manipolare i dipendenti e farsi inviare denaro o dati riservati a loro insaputa.

### Come funziona?
Non si basa sullo sfruttamento di falle software o malware, ma sull'ingegneria sociale; l'attaccante sfrutta l'autorità o una relazione commerciale d'affari per convincere la vittima che la richiesta sia legittima.

La prassi è più o meno:

- L'attaccante viola la vera casella email (magari tramite credenziali rubate) oppure crea un dominio quasi identico a quello originale (detto typosquatting, es. `fornitore-azienda.com` al posto di `fornitore.com`).

- Studia contesto e abitudini, legge le conversazioni interne per settimane per capire stile di scrittura, scadenze dei pagamenti, fatture in sospeso e ruoli aziendali chiave.

- Invia un'email mirata (es. una richiesta improvvisa di cambio IBAN per una fattura o un ordine di bonifico urgente da parte del CEO), facendo pressione affinché il saldo venga eseguito subito e in riservatezza.

### In che modo è diverso da phishing?
Phishing è un termine più generale, che indica l'utilizzo di comunicazioni fraudolente per ingannare la vittima; BEC invece è una forma di frode mirata ai contesti aziendali, in cui l'attaccante impersona una certa identità aziendale.

### Come si previene?
La difesa principale consiste nel verificare l'identità del mittente e l'autenticità delle richieste ricevute:

- **Verifica fuori banda (Out-of-Band):** conferma qualsiasi modifica importante tramite un secondo canale, es. una chiamata telefonica.

- **Autenticazione avanzata dell'email:** configurazione dei DNS della mail per impedire agli attaccanti di spedire contraffacendo il nome dell'azienda.

- **Doppia approvazione:** introduci processi che richiedono l'autorizzazione di almeno due persone per pagamenti sopra una certa soglia.

- **Banner sulle email esterne:** configurazione dei server di posta per mostrare un avviso visivo in cima ai messaggi che provengono da domini esterni all'organizzazione.

---
[[Cross-Site Scripting (XSS)]]
[[Man-in-the-Middle (MitM)]]