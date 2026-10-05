---
date: 2024-12-11
tags:
  - informatica
  - pubblico

---
# Signaling e relay servers in Rustdesk
---
RustDesk utilizza **due tipi di server** per gestire le connessioni:

-  **Signaling Server**:
	- Serve per scambiare informazioni iniziali tra i dispositivi che vogliono connettersi.
	- Ogni dispositivo che esegue RustDesk comunica regolarmente con questo server per fargli sapere qual è il suo IP e la porta attuale.
	- Quando avvii una connessione, il computer A chiede al Signaling Server come contattare il computer B.
	  
- **Relay Server**:
    - Se i due dispositivi non riescono a connettersi direttamente (a causa di NAT o firewall), il Relay Server fa da "ponte" e trasmette i dati tra di loro.

#### **Come funziona una connessione in RustDesk?**
RustDesk permette a due dispositivi di comunicare tramite hole punching per impostazione predefinita, in alternativa viene utilizzato il relay server.

- **Hole Punching** (connessione diretta):
    1. Il Signaling Server cerca di connettere i dispositivi A e B direttamente, "bucando" il NAT (tecnica chiamata **hole punching**).
    2. Questo è il caso più comune, e di solito funziona bene: i dati viaggiano direttamente tra i dispositivi senza passare dal Relay Server.
      
- **Relay Server come piano B**:
    1. Se il hole punching fallisce (ad esempio, per reti troppo restrittive), la connessione usa il Relay Server per instradare i dati.
    2. In questo caso, la qualità della connessione dipende dalle prestazioni del Relay Server.

---

### **Perché potresti voler self-hostare il server RustDesk?**

1. **Connessione più veloce e affidabile**:
    
    - I server pubblici di RustDesk sono progettati per test e ricerca e non per gestire traffico elevato.
    - Questo può causare ritardi nell'avvio delle connessioni, soprattutto quando i server pubblici sono sovraccarichi.
2. **Riduzione della latenza nei casi di Relay**:
    
    - Se la connessione deve passare attraverso un Relay Server, avere un tuo server vicino geograficamente migliora la velocità e la stabilità.
3. **Controllo dei tuoi dati**:
    
    - Usando un server self-hosted, gestisci tu tutto il traffico e le informazioni, aumentando la privacy.

---

### **Cosa non cambia con un server self-hosted?**

- **Velocità dopo la connessione diretta**:
    - Se la connessione diretta tra A e B riesce (hole punching), i dati viaggiano direttamente tra i dispositivi senza passare dal server. In questo caso, il server non influisce sulla velocità o sulla latenza.

---

### **Riassunto semplice**

- RustDesk usa un Signaling Server per aiutare i dispositivi a trovarsi e un Relay Server come backup per instradare i dati.
- La maggior parte delle connessioni usa il hole punching e non passa per il Relay Server.
- **Self-hostare** un server migliora l'affidabilità dell'inizio delle connessioni e riduce la latenza se il Relay Server deve essere usato.
- I server pubblici sono meno stabili perché non progettati per carichi elevati.

---
