---
date: 2026-08-20
tags:
  - informatica
  - pubblico

---
# Telnet (Telecommunication Network)
---
Protocollo di rete applicativo utilizzato per accedere da remoto a computer o apparati di rete (router, switch, server) tramite CLI.

Nato negli anni '70, è uno dei protocolli più vecchi della suite TCP/IP e utilizza di default la porta TCP 23.

 Il nome deriva dalle vecchie telescriventi (teletypewriters, o TTY), i terminali fisici degli anni '60/'70 usati per inviare e ricevere testo dai mainframe; nasceva infatti con lo scopo di simulare una telescrivente connessa attraverso una rete (quindi network).

### Uso di base
Lanci il comando con la sintassi `telnet [IP/Hostname] [Porta]`  

es. `telnet 192.168.1.1 80`

### Problemi di sicurezza
Telnet ha un grave problema: tutto il traffico trasmesso (inclusi nomi utente, password e comandi digitati) viaggia sulla rete in testo semplice senza alcuna cifratura. Un attaccante sulla stessa rete può facilmente catturare i pacchetti con uno sniffer (es. Wireshark).

### Stato attuale
È considerato completamente obsoleto e pericoloso per la gestione remota; è stato sostituito ovunque da SSH, che cifra l'intero canale di comunicazione.

Nonostante sia sconsigliato per la gestione dei sistemi, viene ancora usato da tecnici e amministratori di rete come strumento rapido per verificare se una specifica porta TCP su un server remoto è aperta ed esposta (es. `telnet 192.168.1.1 80`).


---
[[SSH (Secure Shell)]]