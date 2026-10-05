---
date: 2026-05-12
tags:
  - informatica
  - linux
  - pubblico

---
# curl (client URL)
---
Comando [[Linux]] utilizzato per trasferire dati da o verso un server tramite URL, supporta diversi protocolli di rete come HTTP, HTTPS, FTP e SFTP.

È molto usato per testare API, scaricare file e verificare la raggiungibilità di servizi web.

### Scaricare il contenuto di una pagina web
Lanci il comando con la sintassi `curl [URL]`

es.

```bash
curl https://example.com
```

Il codice HTML della pagina viene stampato nel terminale.

### curl -O (Remote Name)
Salva un file utilizzando il nome originale presente nell'URL.

Lanci il comando con la sintassi `curl -O [URL]`

es.

```bash
curl -O https://example.com/file.zip
```

### curl -o (Output)
Salva un file con un nome specificato dall'utente.

Lanci il comando con la sintassi `curl -o [nome_file] [URL]`

es.

```bash
curl -o backup.zip https://example.com/file.zip
```

### curl -I (Head)
Stampa a terminale solamente gli header della risposta HTTP.

Lanci il comando con la sintassi `curl -I [URL]`

es.

```bash
curl -I https://example.com
```

### curl -X (Request Method)
Specifica il metodo HTTP da utilizzare.

Lanci il comando con la sintassi `curl -X [metodo] [URL]`

es.

```bash
curl -X POST https://example.com/api
```

### curl -L (Location)
Segue automaticamente i redirect HTTP.

Lanci il comando con la sintassi `curl -L [URL]`

es.

```bash
curl -L https://example.com
```


---
