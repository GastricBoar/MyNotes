---
date: 2026-08-14
tags:
  - informatica
  - pubblico

---
# WPS (Wi-Fi Protected Setup)
---
Standard creato dalla Wi-Fi Alliance nel 2006 con l'obiettivo di semplificare l'associazione dei dispositivi a una rete Wi-Fi protetta, evitando all'utente di dover digitare a mano password lunghe e complesse.

### Come funziona?
Mette a disposizione due modalità per connettere dispositivi alla rete:

* **PBC (Push Button Configuration):** premi un pulsante WPS fisico sul router (o virtuale da pannello di controllo), entro due minuti premi il tasto WPS sul dispositivo da connettere, e i due stabiliscono la connessione.
  
* **PIN:** un codice a 8 cifre stampanto sull'etichetta del router, lo digiti sul dispositivo sul quale accedere; al contrario puoi avere un PIN su dispositivo da inserire all'interno della pagina di configurazione del router.

### Vulnerabilità e stato attuale
Ad oggi è consigliato disattivare completamente le funzioni WPS, a causa di una grave falla di sicurezza che riguarda il modo in cui il PIN viene elaborato:

- Il PIN è lungo 8 cifre, ma il sistema di verifica invia risposte separate per le prime 4 cifre e per le altre 3 successive, mentre l'ultima cifra è solo un checksum quindi non aggiunge ulteriore protezione.
- Un malintenzionato potrebbe far brute-force delle combinazioni richieste, essendo solo 11.000.

Al giorno d'oggi tutti i principali sistemi operativi moderni hanno rimosso il supporto a WPS, in favore di codici QR o lo standard Wi-Fi Easy Connect (DPP) di WPA3, che usa QR o NFC per l'associazione dei dispositivi.

---
