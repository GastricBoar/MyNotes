---
date: 2026-10-30-22-47
tags:
  - informatica
  - pubblico
---
# DevOps
---
Un insieme di pratiche tecniche e culturali per favorire la collaborazione tra programmatori (development) e sistemisti (operations). L'obiettivo è rendere il rilascio del software più rapido, affidabile e ripetibile.

### Il contesto
Tradizionalmente, i team di sviluppo e quelli operativi lavoravano con obiettivi e responsabilità differenti: gli sviluppatori realizzano nuove funzionalità, e i sistemisti mantengono stabile l'infrastruttura che regge quel codice.

Questa separazione era a volte motivo di conflitti, pensa a questo: 

- Programmatore dice "Pubblichiamo questa nuova funzionalità".
- Sistemista dice "Sul server di produzione usiamo una versione di Python diversa dal tuo ambiente di sviluppo, quell'applicazione potrebbe non funzionare".
- Programmatore insiste "Ma sul mio pc funziona".
- Sistemista dice "Non possiamo rischiare di mandare offline il servizio per pubblicare una modifica non verificata."

Come vedi, una modifica utile allo sviluppo poteva introdurre problemi nell'infrastruttura di produzione, e viceversa, le esigenze di stabilità dell'infrastruttura potevano rallentare il rilascio di nuove funzionalità.

DevOps nasce per ridurre questa distanza.

### Come funziona?
Nel concreto, è un misto tra una serie di pratiche tecniche e una certa predisposizione mentale nell'inquadrare la collaborazione tra sviluppatori e sistemisti. 

![Pasted image 20261031111423.png](Utilities/Media/Pasted%20image%2020261031111423.png)

#### Automazione
Automatizzare le attività ripetitive, dalla configurazione dei server all'esecuzione dei test e al rilascio del software.

Include strumenti come:

- **Ansible:** automatizzi la configurazione di sistemi e attività amministrative, es. installi pacchetti, modifichi file di configurazione e avvi servizi su più server contemporaneamente.

- **Jenkins o GitHub Actions:** automatizzi l'esecuzione dei test e il rilascio del software, es. esegui test automatici a ogni modifica del codice e distribuisci una nuova versione dell'applicazione (più precisamente, si chiamano pipeline CI\CD).

- **Terraform:** automatizzi la creazione e la gestione dell'infrastruttura tramite codice, es. crei macchine virtuali e configuri reti attraverso file di configurazione.

#### Standardizzazione
Rendere riproducibili ambienti e configurazioni, evitando differenze impreviste tra sviluppo e produzione; previene il problema del "Sul mio PC funzionava".

Include strumenti come:

- **Docker o Podman:** standardizzi l'esecuzione delle applicazioni tramite ambienti isolati (i container), es. impacchetti dentro container un'applicazione con tutte le sue dipendenze puoi eseguirla su macchine diverse senza doverle riconfigurare manualmente.

- **Git:** tieni traccia di modifiche al codice e ai file di configurazione.

- **Terraform e Ansible:** come visto prima, definisci e rendi riproducibili l'infrastruttura e la configurazione dei sistemi tramite codice.

#### Monitoraggio
Raccogliere informazioni sul funzionamento di applicazioni e infrastruttura per individuare problemi e migliorarne l'affidabilità.

Include strumenti come:

- **Prometheus:** raccogli metriche dai sistemi, es. l'utilizzo della CPU, della RAM e lo stato dei servizi.

- **Grafana:** visualizzi quelle metriche attraverso dashboard, analizzi l'utilizzo delle risorse dei server nel tempo.

- **Loki o Elasticsearch:** raccogli e consulti i log, individui gli errori registrati da un'applicazione dopo un rilascio.

#### Collaborazione
Condividere informazioni, obiettivi e responsabilità tra sviluppo e operations durante tutto il ciclo di vita del software.

Include strumenti come:

- **GitHub o GitLab:** collabori attraverso repository di codice condivisi.

- **Jira:** organizzi attività, segnalazioni e problemi.

- **Mattermost, Slack o Fluxer:** condividi informazioni e notifiche operative con altre persone, es. ricevi una notifica quando una pipeline CI/CD fallisce o un servizio presenta un problema.


---