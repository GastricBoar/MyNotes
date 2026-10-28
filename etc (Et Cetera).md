---
date: 2026-07-06
tags:
  - informatica
  - linux
  - pubblico

---
# /etc (Et Cetera)
---
La directory di [[Linux]] che contiene file di configurazione del sistema e dei servizi installati.

### Come funziona?
Nonostante il nome significhi "et cetera", oggi è la directory standard per i file di configurazione del sistema; storicamente era invece destinata a contenere file di sistema "vari". 

Per nominare alcuni file importanti in una tabella:

| File                   | Descrizione                                      |
| ---------------------- | ------------------------------------------------ |
| `/etc/passwd`          | Informazioni sugli utenti del sistema.           |
| `/etc/shadow`          | Hash delle password degli utenti.                |
| `/etc/group`           | Definizione dei gruppi del sistema.              |
| `/etc/hostname`        | Nome host della macchina.                        |
| `/etc/hosts`           | Associazione tra nomi host e indirizzi IP.       |
| `/etc/fstab`           | Configurazione dei filesystem montati all'avvio. |
| `/etc/resolv.conf`     | Configurazione dei server DNS.                   |
| `/etc/ssh/sshd_config` | Configurazione del server OpenSSH.               |
| `/etc/sudoers`         | Configurazione dei privilegi di `sudo`.          |
| `/etc/os-release`      | Informazioni sulla distribuzione installata.     |

Per nominare alcune directory importanti in una tabella:

| Directory | Descrizione |
|-----------|-------------|
| `/etc/ssh/` | Configurazione di OpenSSH. |
| `/etc/systemd/` | Configurazione di systemd. |
| `/etc/network/` | Configurazione della rete (in alcune distribuzioni). |
| `/etc/pacman.d/` | Configurazione di Pacman (Arch Linux). |
| `/etc/apt/` | Configurazione di APT (Debian/Ubuntu). |

---
[[Filesystem Linux]] | [[/home]] | [[/var]] | [[/usr]]