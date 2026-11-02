---
date: 2026-11-03-20-00
tags:
  - informatica
  - pubblico
---
# Cloud Native
---
Approccio alla progettazione e gestione delle applicazioni pensato per rendere le applicazioni automatizzabili, scalabili, resilienti e facilmente distribuibili; queste sono tutte caratteristiche tipiche degli ambienti cloud.

### Il contesto
Tradizionalmente, le applicazioni venivano progettate come un unico blocco monolitico: tutto installato ed eseguito su un server, con le sue componenti strettamente collegate. È il caso di un gestionale che ingloba autenticazione degli utenti, gestione dei documenti, elaborazione dei dati e generazione di report tutte all'interno della stessa applicazione.

Questo approccio crea alcune difficoltà:
- Se una componente dell'applicazione ha un problema, può compromettere l'intero servizio.
- Aumentare le risorse disponibili per l'applicazione richiede interventi manuali.
- Aggiornare una singola componente richiede di distribuire nuovamente l'intera applicazione.

L'avvento delle infrastrutture cloud ha reso più accessibile disporre di risorse dinamiche, distribuite e facilmente scalabili; di conseguenza è diventato più importante e conveniente progettare applicazioni che queste capacità le possano sfruttare.

L'approccio Cloud Native nasce da questa esigenza, e non significa necessariamente utilizzare servizi cloud: si può adottare anche su infrastrutture on-premise, purché vengano progettate per garantire scalabilità, resilienza e automazione.

### Come funziona?
Si basa su una serie di tecnologie e principi.

#### Containerizzazione
Impacchettare applicazioni e dipendenze in ambienti isolati (es. i container), rende più semplice e uniforme la distribuzione su sistemi diversi.

Include strumenti come:

- **Docker o Podman:** crei ed esegui container che includono un'applicazione e le sue dipendenze.
- **containerd:** runtime che permette di eseguire e gestire container.

#### Microservizi
Suddividere un'applicazione in componenti indipendenti, ognuna si occupa di una specifica funzionalità; è utile perchè ogni componente può essere sviluppata, distribuita e aggiornata separatamente.

Ad esempio, un software di monitoraggio può avere servizi distinti per la raccolta di metriche, la gestione degli alert e l'autenticazione degli utenti.

Include tecnologie come:

- **Spring Boot:** sviluppi servizi applicativi indipendenti utilizzando Java.
- **Go:** sviluppi servizi leggeri e autonomi, particolarmente adatti ad applicazioni distribuite.
- **gRPC:** permetti la comunicazione tra servizi attraverso chiamate remote (RPC).

#### Orchestrazione
Automatizzare la distribuzione, l'esecuzione e la gestione dei container, coordinandoli tra una o più macchine.

Include strumenti come:

- **Kubernetes:** distribuisci e gestisci container su più macchine, automatizzando operazioni come il riavvio dei container guasti e la scalabilità delle applicazioni.
- **Helm:** installi e gestisci applicazioni su Kubernetes attraverso pacchetti chiamati chart.
- **containerd:** fornisce il runtime utilizzato da Kubernetes per eseguire i container.

#### Scalabilità e resilienza
Progettare applicazioni capaci di adattarsi alle variazioni del carico di lavoro e continuare a funzionare anche in presenza di guasti.

Include strumenti e tecnologie come:
- **Kubernetes:** aumenta o riduce automaticamente il numero di istanze di un'applicazione in base a determinate condizioni e ne ripristina quelle che smettono di funzionare.
- **HAProxy:** distribuisci le richieste tra più istanze di un'applicazione attraverso il bilanciamento del carico (load balancing).
- **Istio:** gestisci la comunicazione tra microservizi.

#### Observability
Raccogliere e analizzare informazioni sul comportamento delle applicazioni per monitorarne lo stato, individuare anomalie e diagnosticare problemi.

Include strumenti come:
- **Prometheus:** raccogli metriche, ad esempio utilizzo della CPU, memoria e numero di richieste al secondo.
- **Grafana:** visualizzi metriche e informazioni attraverso dashboard.
- **Loki:** raccogli e consulti i log delle applicazioni.
- **Jaeger:** analizzi le tracce delle richieste che attraversano più servizi.

### La Cloud Native Computing Foundation (CNFC)
È una fondazione che promuove lo sviluppo di tecnologie open source Cloud Native. [Qui ci sta il loro landscape.](https://landscape.cncf.io/)

---
[[Container]]