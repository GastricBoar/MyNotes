---
date: 2026-07-01
tags:
  - informatica
  - linux
  - pubblico

---
# ip (IP Utility)
---
Comando [[Linux]] utilizzato per visualizzare e gestire la configurazione di rete del sistema.

Fa parte della suite iproute2 ed è il sostituto moderno di comandi come `ifconfig`, `route` e `arp`.

### Visualizzare le interfacce di rete

Lanci il comando con la sintassi:

```bash
ip l
```

Mostra le interfacce di rete e il loro stato, puoi anche usare `ip link`.

### Visualizzare gli indirizzi IP

Lanci il comando con la sintassi:

```bash
ip a
```

Mostra gli indirizzi IPv4 e IPv6 assegnati alle interfacce, puoi anche usare `ip addr`.

### Visualizzare la tabella di routing

Lanci il comando con la sintassi:

```bash
ip r
```

Mostra le rotte utilizzate dal sistema per raggiungere le varie reti, puoi anche usare `ip route`.

### Attivare un'interfaccia

Lanci il comando con la sintassi:

```bash
sudo ip link set eth0 up
```

### Disattivare un'interfaccia

Lanci il comando con la sintassi:

```bash
sudo ip link set eth0 down
```

### Assegnare un indirizzo IP

Lanci il comando con la sintassi:

```bash
sudo ip addr add 192.168.1.10/24 dev eth0
```

### Rimuovere un indirizzo IP

Lanci il comando con la sintassi:

```bash
sudo ip addr del 192.168.1.10/24 dev eth0
```

Ricorda che le modifiche effettuate con `ip` sono temporanee e vengono perse al riavvio, a meno che non vengano salvate nella configurazione di rete della distribuzione.

---