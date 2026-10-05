---
date: 2026-08-30
tags:
  - informatica
  - pubblico

---
# SAML (Security Assertion Markup Language)
---
Standard che definisce il modo in cui un Identity Provider (IdP) comunica a un Service Provider (SP) l'identità e il risultato dell'autenticazione di un utente, permettendo di implementare il Single Sign-On (SSO).

### Il contesto
Un'azienda utilizza diversi servizi online, e ogni servizio gestisce autonomamente l'autenticazione dei propri utenti: hai un account Slack, un account GitHub, un account Salesforce, ciascuno con le proprie credenziali. Questi servizi li chiamiamo Service Provider (SP).

Per evitare questo, puoi centralizzare la gestione delle identità tramite un Identity Provider (IdP), che si occupa di autenticare gli utenti e comunicare ai vari servizi la loro identità. Tra i più conosciuti trovi Microsoft Entra ID, Okta o Google Workspace.

SAML è lo standard che regola questa comunicazione tra l'Identity Provider e i servizi che l'utente vuole utilizzare.

### Come funziona?
Mettiamo tu voglia accedere a Slack in azienda che usa Okta come identity provider:
   
- Slack, che qui è il service provider, riconosce che la tua organizzazione utilizza Okta come identity provider e ti reindirizza verso di esso.
   
- Okta ti autentica chiedendoti username e password.
   
- Una volta autenticato, genera una SAML assertion, un documento XML che dice a Slack "questo utente è Mario ed è stato autenticato".
   
- Slack verifica la SAML assertion e ti concede l'accesso.

Come vedi, è l'identity provider che ti autentica; SAML definisce invece il modo standard con il quale l'identity provider comunica al service provider il risultato di quell'autenticazione, e altre informazioni.

SAML è comunemente utilizzato per implementare Single Sign-On in applicazioni web aziendali.

---