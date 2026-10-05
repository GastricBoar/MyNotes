---
date: 2026-08-20
tags:
  - informatica
  - pubblico

---
# SSH (Secure Shell)
---
Protocollo di rete applicativo che consente di accedere e gestire da remoto computer o apparati di rete tramite riga di comando, in modo completamente cifrato e sicuro; utilizza di default la porta TCP 22.

È nato per sostituire i vecchi protocolli non protetti come Telnet, rlogin e FTP.

### Uso di base
Lanci il comando con la sintassi `ssh [utente]@[IP/Hostname] [-p porta]`

es. `ssh admin@192.168.1.1` oppure `ssh admin@192.168.1.1 -p 2222`

### Come funziona?
A differenza di Telnet, SSH cifra l'intero canale di comunicazione (comandi, password e dati trasferiti) proteggendolo da intercettazioni (sniffing) e attacchi Man-in-the-Middle.

L'autenticazione avviene tramite password oppure tramite coppia di chiavi crittografiche, offrendo un livello di sicurezza ancora più elevato. Per fare un esempio:

- Crei una coppia di chiavi sul tuo PC locale con il comando `ssh-keygen`, questo genera una chiave privata e una chiave pubblica.
- La chiave privata deve restare segreta, la tieni sul tuo PC.
- La chiave pubblica la copi su server remoto, per esempio dentro `~/.ssh/authorized_keys` usando il comando `ssh-copy-id admin@192.168.1.1`.
- Da quel momento in poi, connettersi in ssh non richiederà alcuna password, perchè il tuo PC ti autentica tramite controllo crittografico.

### Funzionalità aggiuntive
Oltre all'accesso alla riga di comando, SSH tioffre diverse funzionalità avanzate:

- **Trasferimento file sicuro:** supporta i protocolli SFTP e SCP per copiare file in modo cifrato tra due host.

- **SSH tunneling:** ti permette di incapsulare il traffico di altre applicazioni non sicure all'interno del canale cifrato di SSH.

---
