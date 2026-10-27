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
Il kernel lancia systemd come primo processo dello user space all'avvio del sistema, prende PID 1; da quel momento, gestisce servizi e altri componenti, che chiamiamo "unità".

Un'unità è una risorsa gestibile da systemd, e ogni unità ha un suo file di configurazione detto "unit file". Ci sono diversi tipi di unità:

- **Service:** rappresenta un servizio o un processo gestito da `systemd`, il suo unit file ha estensione `.service`; per esempio, `ssh.service` definisce come gestire il servizio SSH.

- **Timer:** pianifica l'attivazione di altre unità in determinati momenti, il suo unit file ha estensione `.timer`; per esempio, `apt-daily.timer` pianifica l'esecuzione di attività automatiche per aggiornare gli indici dei pacchetti.

- **Socket:** rappresenta un socket gestito da `systemd`, che può attivare un servizio quando necessario, il suo unit file ha estensione `.socket`; per esempio, `ssh.socket` può attendere connessioni SSH e attivare il servizio SSH nel momento in cui arriva una richiesta.

- **Mount:** rappresenta un punto di montaggio di un filesystem gestito da `systemd`, il suo unit file ha estensione `.mount`; per esempio, `home.mount` definisce come montare un filesystem nella directory `/home`.

- **Target:** raggruppa unità per coordinare l'avvio e il funzionamento del sistema, il suo unit file ha estensione `.target`; per esempio, `multi-user.target` identifica uno stato del sistema in cui sono disponibili i servizi necessari per l'uso in modalità multiutente, generalmente senza interfaccia grafica.

Lo unit file di ciascuna unità definisce il modo in cui systemd deve gestirla, avviarla, arrestarla o quali altre attività convolgere.

Gli unit file si trovano in queste directory:

- `/usr/lib/systemd/system/`: unit file installati dai pacchetti del sistema.
- `/etc/systemd/system/`: unit file creati dall'amministratore e personalizzazioni delle unità esistenti.
- `/run/systemd/system/`: unit file creati temporaneamente durante l'esecuzione del sistema.

Gli unit file sono leggibili, se lanci `systemctl cat sshd.service` vedi:

```
# /usr/lib/systemd/system/sshd.service
[Unit]
After=network.target sshdgenkeys.service
Before=ssh-access.target
Description=OpenSSH Daemon
Documentation=man:sshd(8) man:sshd_config(5)
Wants=sshdgenkeys.service ssh-access.target

[Service]
Type=notify-reload
ExecStart=/usr/bin/sshd -D
KillMode=process
Restart=always

[Install]
WantedBy=multi-user.target
```

### I componenti
Con gli anni systemd è cresciuto così tanto da diventare molto più di un gestore di servizi; ad oggi è una grossa suite di componenti che si occupa di tante cose:

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