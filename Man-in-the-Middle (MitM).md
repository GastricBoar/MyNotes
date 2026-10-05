---
date: 2026-09-01
tags:
  - informatica
  - pubblico

---
# Man-in-the-Middle (MitM)
---
Tipo di attacco informatico in cui un malintenzionato si interpone segretamente tra due parti (es. l'utente e un sito web) intercettando, e potenzialmente alterando, le comunicazioni a loro insaputa.

### Come funziona?
Non esiste un unico Man-in-the-Middle, ma diverse varianti a seconda del mezzo di comunicazione che viene compromesso (es. email, wireless, sessioni web e persino chiamate VoIP); una cosa è però comune: l'attaccante si posiziona al centro della conversazione facendo credere a entrambe le vittime di star comunicando direttamente tra loro.

Da lì:

- Forza il traffico di rete a passare attraverso il proprio dispositivo (es. tramite una falsa rete Wi-Fi o manipolando i protocolli di rete).

- I dati trasmessi (credenziali, numeri di carta di credito, messaggi) vengono letti o alterati dall'attaccante in tempo reale.

- Il traffico viene comunque reindirizzato al vero destinatario, in modo che nessuna delle due parti si accorga dell'intrusione.

### Come si previene?
La difesa principale consiste nel verificare l'identità dell'interlocutore e proteggere la comunicazione, in modo che l'attaccante non possa impersonare una delle due parti o leggere e modificare i dati.

- **Usa HTTPS/TLS**: il certificato digitale permette al client di verificare che la chiave pubblica appartenga realmente al sito con cui vuoi comunicare.
  
- **Usa una VPN:** il canale autenticato e cifrato tra i dispositivi rende più difficile intercettare o alterare il traffico.
  
- **Utilizza un Wi-Fi sicuro:** reti protette con protocolli moderni come WPA2 o WPA3 invece di reti aperte.
  
- **Autentica dove puoi:** per esempio, meccanismi come MFA rendono più difficile per l'attaccante utilizzare credenziali intercettate.
  
- **Certificati e firme digitali:** come per HTTPS, permettono di verificare l'autenticità e l'integrità delle informazioni ricevute.

---
