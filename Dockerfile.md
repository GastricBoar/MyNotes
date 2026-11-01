---
date: 2026-11-02-14-39
tags:
  - informatica
  - pubblico
---
# Dockerfile
---
File di testo che contiene le istruzioni necessarie per costruire un'immagine Docker.

### Come funziona?
Per funzionare, un'applicazione ha bisogno di un ambiente che includa il linguaggio di programmazione, le librerie e tutte le dipendenze necessarie. Un container è perfetto a questo scopo, perchè l'applicazione viene eseguita assieme a tutto ciò di cui ha bisogno nel proprio ambiente isolato, ma da dove arriva questo ambiente?

I container altro non sono che istanze di un'immagine Docker: template in sola lettura che contengono filesystem, dipendenze e configurazioni per creare container.

A questo punto la domanda sorge spontanea: se le immagini Docker sono template in sola lettura, cosa crea un'immagine Docker? un Dockerfile, che è un file di testo contenente le istruzioni necessarie a costruire l'immagine; p.s un Dockerfile non ha estensione.

Le istruzioni principali di questo Dockerfile sono:
#### FROM
Specifica l'immagine di base da utilizzare, es. `python:3.12`; il Dockerfile non contiene l'immagine in sè, ma ne indica il riferimento, che sia in locale o su web.

#### WORKDIR
Definisce la directory di lavoro all'interno dell'immagine, es. `/app`; le istruzioni successive verranno eseguite partendo da questa directory.

#### COPY
Copia file e directory dal sistema host all'immagine, es. `COPY app.py /app/` copia il file `app.py` del sistema host nella directory `/app/` dell'immagine.

#### RUN
Esegue comandi durante la costruzione dell'immagine, es. `RUN pip install flask`.

#### CMD
Definisce il comando predefinito da eseguire quando viene avviato un container, es. `CMD ["python", "app.py"]` avvia l'applicazione Python, ed è come se stessi lanciando il comando `python app.py` da terminale.

Docker supporta due forme di sintassi per il comando CMD:

- **La exec form:** utilizza parentesi quadre per separare il programma dai suoi argomenti, il risultato è un array del tipo `CMD ["python", "app.py"]`. In questo esempio, Python viene avviato come processo principale del container (con PID 1) e riceve direttamente i segnali di arresto inviati da Docker.

- **La shell form**: esegue il comando attraverso una shell, es. `CMD python app.py`. In questo caso è la shell che diventa il processo principale (con PID 1), con Python come processo figlio.

La exec form è generalmente preferibile, perché avvia direttamente Python come processo principale del container; nella shell form, invece, la shell (che è il processo principale) potrebbe non inoltrare correttamente questi segnali al processo figlio.

Un Dockerfile di esempio assomiglia a:

```dockerfile
# Immagine di base
FROM python:3.12

# Directory di lavoro
WORKDIR /app

# Copia dipendenze dal sistema host alla directory /app/ dell'immagine; usa "." perché WORKDIR aveva impostato la directory di destinazione.
COPY requirements.txt .

# Installa le dipendenze
RUN pip install -r requirements.txt

# Copia il codice dell'applicazione
COPY app.py .

# Comando da eseguire all'avvio del container
CMD ["python", "app.py"]
```

### Differenza tra Dockerfile, immagine e container
Come accennato su:

- **Il Dockerfile** contiene le istruzioni per costruire un'immagine.
- **L'immagine** è il modello immutabile contenente il filesystem e le configurazioni necessarie per creare un container.
- **Container:** è l'istanza in esecuzione di un'immagine.

---
[[Container]]