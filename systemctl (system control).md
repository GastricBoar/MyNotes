---
date: 2026-10-27-22-03
tags:
  - informatica
  - pubblico
---
# systemctl (system control)
---
Comando Linux utilizzato per consultare e controllare lo stato di `systemd`, il gestore dei servizi e delle unità di sistema.

#### systemctl status
Ti permette di verificare lo stato di un servizio, se è attivo e informazioni sul suo funzionamento.

Lanci il comando con la sintassi `systemctl status [servizio]`:

```bash
systemctl status sshd
```

#### systemctl start
Avvia il servizio, senza però configurarlo per l'avvio automatico all'accensione del sistema.

Lanci il comando con la sintassi `systemctl start [servizio]`:

```bash
systemctl start sshd
```

#### systemctl enable
Configura un servizio per l'avvio automatico all'accensione del sistema.

Lanci il comando con la sintassi `systemctl enable [servizio]`:

```bash
systemctl enable sshd
```

#### systemctl enable --now
Configura l'avvio automatico all'accensione del sistema, e avvia immediatamente il servizio.

Lanci il comando con la sintassi `systemctl enable --now [servizio]`:

```bash
systemctl enable --now sshd
```

#### systemctl list-units
Elenca le unità attualmente caricate da `systemd`:

```bash
systemctl list-units --type=service
```

---
[[systemd]]