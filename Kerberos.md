---
date: 2026-08-17
tags:
  - informatica
  - pubblico

---
# Kerberos
---
Protocollo di autenticazione di rete progettato per verificare in modo sicuro l'identità di utenti e dispositivi su una rete non protetta; utilizza un sistema centrale basato su biglietti temporanei, detti "tickets".

È il protocollo di autenticazione primario e predefinito utilizzato negli ambienti Microsoft Active Directory, ma è supportato anche su Linux e macOS per l'integrazione in reti aziendali strutturate.

### Le componenti
Il sistema si basa sull'interazione tra tre entità principali:

- **Il client:** l'utente o la macchina che richiede l'accesso a una risorsa.
  
-  **KDC (Key Distribution Center):** l'autorità centrale fidata, composto a sua volta da:
  
   1. **AS (Authentication Server):** autentica l'utente all'inizio (es. la mattina) e rilascia il biglietto generale di ingresso, detto "Ticket Granting Ticket" (TGT).

   2.  **TGS (Ticket Granting Server):** riceve il TGT e rilascia i biglietti specifici per i singoli servizi (Service Ticket).

- **Il service server:** server finale che eroga la risorsa (es. file server, stampante, web server).
  
### Come funziona?
Anziché trasmettere la password dell'utente ogni volta che si tenta di accedere a una risorsa di rete (file server, stampante, database), Kerberos centralizza la fiducia sul server KDC dedicato.

La password viene usata una sola volta al momento del login iniziale; da quel momento in poi, l'accesso ai singoli servizi avviene esclusivamente tramite l'esibizione di ticket cifrati.

**Nello specifico:**

- Vuoi accedere alla cartella `\\share\dati` a partire dal tuo PC.

- Al mattino inserisci la password per accedere al tuo PC. Lui invia una richiesta all'authentication server del KDC.
  
- L'AS verifica le credenziali e restituisce il TGT. La tua password viene subito rimossa dalla memoria RAM del PC.

- Quando fai doppio clic per accedere alla cartella condivisa, il client presenta il TGT al TGS chiedendo il permesso di accesso.
  
- Il TGS valida il TGT e genera un service ticket specifico e temporaneo per quella determinata risorsa, la cartella su fileserver.
  
- Il client presenta il service ticket direttamente al service server, che lo convalida ed eroga la risorsa che hai richiesto, senza mai aver visto la tua password.

## Vantaggi
Usare Kerberos è vantaggioso per diversi motivi:

* L'utente inserisce le credenziali una sola volta all'avvio della sessione e può accedere a tutte le risorse autorizzate senza dover reinserire la password, usa Single Sign-On (SSO).
  
* Le password non viaggiano mai sulla rete verso i singoli server di servizio, riduce la superficie d'attacco.
  
* Non solo il server verifica l'identità del client, ma anche il client verifica l'autenticità del server prima di inviare dati sensibili, previene attacchi Man-in-the-Middle.
  
* Ogni biglietto contiene un timestamp a scadenza ravvicinata; se un attaccante intercetta un biglietto, non può riutilizzarlo in seguito perché sarà scaduto.

---
