---
date: 2025-02-01
tags:
  - informatica
  - pubblico

---
# WPA (Wi-Fi Protected Access)
---
Un protocollo di sicurezza per reti [[Wi-Fi]]. Protegge le comunicazioni wireless attraverso autenticazione, [[Crittografia]] e verifica dell'integrità dei dati.

### Il contesto
Il WEP (introdotto nel 1997) era pericolosamente attaccabile: il suo sistema di cifratura RC4 presentava gravi vulnerabilità. IEEE e la Wi-Fi Alliance stavano lavorando a una soluzione definitiva, lo standard IEEE 802.11i, ma i tempi di sviluppo erano troppo lunghi; serviva una soluzione temporanea che potesse essere adottata rapidamente senza sostituire l'hardware esistente.

Cisco, Linksys e altri produttori contribuirono allo sviluppo delle tecnologie alla base di questa soluzione, tra cui [[TKIP (Temporal Key Integrity Protocol)]].

La Wi-Fi Alliance raccolse allora queste tecnologie nel WPA, introdotto nel 2003.

### Modalità di autenticazione
Due diverse modalità di autenticazione, a seconda dell'utilizzo finale che ne si fa.

### WPA-Personal 
Pensata per reti domestiche e piccole reti. Con questa modalità di autenticazione:

- Imposti una password per la rete Wi-Fi, es. "CiaoLondra5". Tutti i dispositivi che si vogliono collegare utilizzano questa password.
  
- La password di rete e l'SSID vengono utilizzati per derivare una Pre-Shared Key (PSK), una chiave crittografica usata per autenticare la sessione di connessione.
  
- Il dispositivo e il router eseguono un handshake per verificare che entrambi conoscano la PSK, senza trasmetterla direttamente.
  
- Durante l'handshake, dispositivo e router calcolano le chiavi temporanee utilizzate per cifrare la comunicazione.

Come vedi, hai ben tre livelli di chiavi differenti: la password che usi per collegarti alla rete, la PSK usata durante l'autenticazione, e le chiavi temporanee per proteggere la comunicazione. In WEP invece, la password che usi per collegarti alla rete viene utilizzata direttamente come chiave di cifratura.

### WPA-Enterprise 
Pensato per reti aziendali, università e organizzazioni di grandi dimensioni. Qui:

- Utilizza un sistema di autenticazione centralizzato, come un server RADIUS o TACACS+, che verifica le credenziali di ogni singolo utente.

- Ogni utente ha le proprie credenziali, invece di condividere un'unica password con tutti gli altri utenti della rete.

### Generazioni del WPA
Negli anni la sicurezza Wi-Fi è stata aggiornata con nuove generazioni:

| Protocollo | Anno | Cifratura       | Autenticazione | Stato            |
| :--------- | :--- | :-------------- | :------------- | :--------------- |
| **WPA**    | 2003 | TKIP / RC4      | PSK / 802.1X   | Deprecato        |
| **WPA2**   | 2004 | AES / CCMP      | PSK / 802.1X   | Diffuso          |
| **WPA3**   | 2018 | AES / CCMP/GCMP | SAE / 802.1X   | Standard moderno |

### WPA2
Il primo membro della famiglia WPA ad utilizzare lo standard [[AES (Advanced Encryption Standard)]] per la crittografia dei dati. È stato un grosso passo in avanti, l'hardware delle schede di rete necessitava di chip dedicati alla crittografia pesante, e quegli anni prima di WPA2 hanno dato tempo al mercato hardware per adeguarsi. 

### WPA3
Introduce l'implementazione  Wi-Fi Enhanced Open (OWE), che cifra e protegge anche le reti pubbliche senza password o autenticazione. Inoltre, grazie al protocollo SAE (Simultaneous Authentication of Equals) e alla Forward Secrecy, blocca gli attacchi offline alla password e impedisce di decifrare il traffico passato anche se la chiave dovesse essere scoperta in seguito. Completa il quadro una modalità a 192 bit, che offre una cifratura opzionale di livello militare pensata per contesti ad altissima sicurezza.


---
[[AAA (Authentication, Authorization, Accounting)]]
[[Wi-Fi]]
[[Progettare una rete wireless aziendale]]
[[RADIUS (Remote Authentication Dial-In User Service)]]
[[TACACS+]]