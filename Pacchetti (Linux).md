---
date: 2026-06-30
tags:
  - informatica
  - pubblico

---
# Pacchetti (Linux)
---
Un archivio contenente uno o più programmi, assieme a file necessari per l'installazione, configurazione e informazioni sulle dipendenze.

### Come funziona?
Tornando alla definizione sopra, è un archivio che contiene:

- **Uno o più programmi:** per esempio il pacchetto openssh-client contiene ssh, scp, sftp, ssh-keygen, ssh-agent e così via.
  
- **File necessari per l'installazione:** come script, metadati su versione, architettura, nome.
  
- **Configurazione:** per esempio nginx installa un suo file di configurazione in `/etc/nginx/nginx.conf`
  
- **Informazioni sulle dipendenze:** un pacchetto non contiene direttamente le dipendenze, ma contiene un elenco delle dipendenze necessarie, che poi verranno scaricate e installate se non sono già presenti a sistema.

I pacchetti vengono gestiti da un package manager che installa, aggiorna, mantiene e rimuove i pacchetti.

### Quali package manager per quali distribuzioni?
Una tabella:

| Distribuzione  | Formato        | Package manager |
| -------------- | -------------- | --------------- |
| Debian, Ubuntu | `.deb`         | `apt`           |
| Fedora, RHEL   | `.rpm`         | `dnf`           |
| Arch Linux     | `.pkg.tar.zst` | `pacman`        |

---
[[apt (Advanced Package Tool)]]
[[dnf (Dandified YUM)]]
[[yum (Yellowdog Updater Modified)]]