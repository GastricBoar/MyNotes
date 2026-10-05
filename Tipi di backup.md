---
date: 2026-06-11
tags:
  - informatica
  - pubblico

---
# Tipi di backup
---
Diversi tipi di backup per scenari diversi.

### Backup completo
Copia l'intero contenuto del tuo disco, semplice e crudo.

### Backup differenziale
Copia tutti i dati modificati dall'ultimo backup completo.

Per fare un esempio:
- domenica hai un backup da 100 GB
- lunedì scrivi altri 5 GB di dati su disco
- martedì fai backup differenziale, e peserà 5 GB
- mercoledì scrivi altri 15 GB di dati su disco
- giovedì fai backup differenziale, e peserà 20 GB

Il vantaggio è la velocità di ripristino da quel backup, è meno dipendente da una catena di backup. Lo svantaggio è lo spazio occupato.

Può convenire per scenari in cui è prioritario il ripristino rapido, come nel caso di server applicativi critici.

### Backup incrementale
Copia solo i dati modificati dall'ultimo backup, incrementale o completo che sia.

Per fare un esempio:
- domenica hai un backup da 100 GB
- lunedì scrivi altri 5 GB di dati su disco
- martedì fai backup incrementale, e peserà 5 GB
- mercoledì scrivi altri 15 GB di dati su disco
- giovedì fai backup incrementale, e peserà 15 GB

Il vantaggio è la velocità di backup, e un'impronta più piccola in spazio e traffico di rete. Lo svantaggio è la velocità di ripristino più lenta rispetto al differenziale.

Può convenire per scenari in cui hai molti dati da proteggere, backup frequenti, ripristini completi poco frequenti e spazio limitato, es. un file server da molti TB.

### Backup completo sintetico
Ricostruisce un backup completo tramite software, senza rileggere dati dal server sorgente.

Per fare un esempio:
- domenica fai un backup completo da 100 GB
- lunedì scrivi altri 5 GB di dati su disco
- martedì fai backup incrementale
- mercoledì scrivi altri 15 GB di dati su disco
- giovedì fai backup incrementale
- venerdì vuoi fare un altro backup completo
- usi un programma che ricombina il backup completo iniziale con i due incrementali fatti
- in questo modo eviti di dover avviare nuovamente un backup completo da 120 GB al server sorgente

Il vantaggio è la velocità di backup, con minore carico sul server e sulla rete. Lo svantaggio è il carico maggiore sul repository di backup.

---