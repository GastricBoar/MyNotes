---
date: 2025-01-31
tags:
  - informatica
  - pubblico

---
# AAA (Authentication, Authorization, Accounting)
---
Un [[Protocollo]] di sicurezza, è utilizzato per controllare l'accesso alle risorse di rete e monitorare l'attività degli utenti.

Come il nome suggerisce, il processo passa da tre funzioni di autenticazione:

- **Authentication (chi sei?):** verifica l'identità dell'utente che sta cercando di accedere alla rete. Questo può succedere in diversi modi: uno username e una password tramite un server [[RADIUS (Remote Authentication Dial-In User Service)]] o [[TACACS+]], un'integrazione con Active Directory, un'autenticazione a due fattori, dei certificati digitali etc.
  
- **Authorization (cosa puoi fare?):** determina a quali risorse di rete puoi accedere, i permessi possono essere configurati in base a criteri scelti tipo ruolo, reparto etc.
  
- **Accounting (cosa hai fatto?):** registra e monitora l'attività degli utenti in rete, son cose come il tempo di connessione, le risorse a cui accedi, i dati trasferiti e altro. Le informazioni vengono raccolte per fatturazione, analisi del traffico, o monitoraggio della sicurezza.


---
[[WLAN (Wireless Local Area Network)]]
[[WAP (Wireless Access Point)]]
[[Wi-Fi]]
[[IEEE 802.11]]
