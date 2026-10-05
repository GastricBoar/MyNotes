---
date: 2026-07-22
tags:
  - informatica
  - linux
  - pubblico

---
# netstat (Network Statistics)
---
Il comando `netstat` è una storica utility di riga di comando usata in [[Linux]] e altri sistemi operativi, per monitorare le connessioni di rete attive (sia in entrata che in uscita), le tabelle di instradamento (routing), le statistiche delle interfacce e i socket in ascolto.

È ormai uno strumento legacy, deprecato in favore del più veloce [[ss (Socket Statistics)]] e del pacchetto `iproute2`.

### Visualizzare tutte le connessioni e le porte
Lanci il comando con la sintassi netstat -a

es.

```bash
netstat -a
```

Il flag -a sta per all e mostra tutte le connessioni attive e le porte in ascolto.

oppure, per mostrare solo le connessioni TCP:

```bash
netstat -at
```

Il flag -t sta per tcp e filtra l'output mostrando solo le connessioni che utilizzano il protocollo TCP.

### Visualizzare le porte in ascolto
Lanci il comando con la sintassi netstat -l

es.

```bash
netstat -l
```

Il flag -l sta per listening e mostra soltanto i socket attualmente pronti ad accettare nuove connessioni.

### Mostrare indirizzi e porte in formato numerico
Lanci il comando con la sintassi netstat -n

es.

```bash
netstat -an
```

Il flag -n sta per numeric e mostra gli indirizzi IP e i numeri di porta invece di convertirli in nomi host e nomi di servizio. Evita la risoluzione dei nomi DNS rendendo l'output più veloce.

### netstat -tulpn (Mostrare i processi in ascolto)
Mostra tutte le porte TCP e UDP in ascolto con il relativo PID e nome del programma.

Lanci il comando con la sintassi:

```bash
sudo netstat -tulpn
```

Quelle flag son spiegate così:
-t (tcp) mostra le connessioni TCP
-u (udp) mostra le connessioni UDP
-l (listening) mostra soltanto i servizi in ascolto
-p (program) mostra il PID e il nome del programma proprietario del socket
-n (numeric) mostra indirizzi IP e porte in formato numerico

### netstat -r (Routing Table)
Mostra la tabella di instradamento della rete.

Lanci il comando con la sintassi:

```bash
netstat -r
```

Il flag -r sta per route e mostra la tabella d'instradamento del kernel, in modo analogo al comando route.

---