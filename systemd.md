---
date: 2026-05-13
tags:
  - informatica
  - linux
  - pubblico

---
# systemd (system daemon)
---
Un sistema di init e service manager utilizzato dalla maggior parte delle distribuzioni Linux.

### Come funziona?
Qui tocca allargare il discorso, perchè con gli anni systemd è cresciuto così tanto da diventare molto più di un gestore di servizi; ad oggi è una grossa suite di componenti che si occupa di tante cose:

- **systemd-journald:** raccoglie e gestisce i log di sistema e servizi, accessibili principalmente tramite `journalctl`.
  
- **systemd-logind:** gestisce le sessioni degli utenti, i login e alcune funzioni legate all'alimentazione.
  
- **systemd-networkd:** gestisce la configurazione e lo stato delle interfacce di rete.
  
- **systemd-resolved:** gestisce la risoluzione DNS.
  
- **systemd-timesyncd:** sincronizza l'orologio del sistema tramite NTP.
  
- **systemd-timer:** permette di pianificare attività automaticamente a intervalli o in determinati momenti, in alternativa a cron.
  
- **systemd-mount:** gestisce i mount point attraverso le unità di systemd.
  
- **systemd-machined:** gestisce e monitora macchine virtuali e container.
  
- **hostnamectl:** permette di visualizzare e modificare l'hostname del sistema.
  
- **timedatectl:** permette di gestire ora, data, fuso orario e sincronizzazione dell'orologio.
  
- **localectl:** permette di configurare lingua, localizzazione e layout della tastiera.

È proprio questa sua progressiva espansione a essere alla base di alcune critiche: secondo alcuni, systemd è diventato troppo monolitico, allontanandosi dalla filosofia UNIX del "fai una cosa e falla bene". La scelta ha comunque permesso di integrare in modo più uniforme molte funzioni fondamentali del sistema Linux.

---
[[Sistema di init]]
[[Linux]]
[[UNIX]]