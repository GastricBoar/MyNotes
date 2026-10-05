---
date: 2026-06-30
tags:
  - informatica
  - pubblico

---
# Pacchetti (Linux)
---
Un archivio contenente uno o più programmi, insieme ai file necessari per l'installazione, alla configurazione e alle informazioni sulle dipendenze.

### Cosa contiene?
Tornando sulla definizione:

- **Uno o più programmi:** per esempio openssh-client contiene ssh, scp, sftp, ssh-keygen, ssh-agent etc.
  
- **File necessari per l'installazione:** come script, metadati su versione, architettura, nome
  
- **Configurazione:** per esempio nginx installa un suo file di configurazione in `/etc/nginx/nginx.conf`
  
- **Informazioni sulle dipendenze:** un pacchetto non contiene direttamente dipendenze, ma un elenco delle dipendenze necessarie, che poi verranno scaricate se non sono già presenti a sistema

### Come vengono gestiti?
Da un package manager, che installa, aggiorna, mantiene e rimuove i pacchetti.

### Quali package manager per quali distribuzioni?

| Distribuzione  | Formato        | Package manager |
| -------------- | -------------- | --------------- |
| Debian, Ubuntu | `.deb`         | `apt`           |
| Fedora, RHEL   | `.rpm`         | `dnf`           |
| Arch Linux     | `.pkg.tar.zst` | `pacman`        |

---
[[apt (Advanced Package Tool)]]
[[dnf (Dandified YUM)]]
[[yum (Yellowdog Updater Modified)]]