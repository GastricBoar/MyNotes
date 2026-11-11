---
date: 2026-11-12-14-52
tags:
  - informatica
  - linux
  - pubblico
---
# scp (Secure Copy)
---
Programma a riga di comando che permette di copiare file verso sistemi remoti utilizzando SSH. 

### Come funziona?
Usa SSH come protocollo di trasporto, la comunicazione è cifrata e l'accesso al sistema remoto avviene tramite autenticazione SSH.

A differenza di `cp`, che copia file tra percorsi locali, SCP permette di trasferire file anche verso e da computer remoti.

### Sintassi
Lanci il comando con la sintassi `scp [file] [destinazione]:[percorso]`:

```bash
scp document.txt paolo@192.168.1.100:/home/paolo/
```

Copia `document.txt` dal tuo PC alla directory `/home/paolo/` del server remoto.

### Scaricare un file dal server remoto
Lanci il comando così:

```bash
scp paolo@192.168.1.100:/home/paolo/document.txt .
```

Il punto alla fine indica la directory corrente del tuo PC.

### Trasferire una directory
Per trasferire un'intera directory e il suo contenuto, utilizzi l'opzione `-r`:

```bash
scp -r backup/ paolo@192.168.1.100:/home/paolo/
```

---
[[cp (copy)]]
[[ssh (comando)]]
[[SSH (Secure Shell)]]