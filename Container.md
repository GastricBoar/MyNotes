---
date: 2026-10-31-12-48
tags:
  - informatica
  - pubblico
---
# Container
---
Ambiente isolato in cui viene eseguita un'applicazione insieme alle sue dipendenze.

### L'esigenza
Immagina di voler sviluppare un'applicazione sul tuo PC e di doverla poi eseguire su un server, o passarla a un amico.: un'applicazione può dipendere da specifiche versioni di un linguaggio di programmazione, librerie o altri componenti software. Se l'ambiente in cui quest'applicazione viene sviluppata è diverso da quello in cui viene eseguita, potrebbe funzionar male.

I container risolvono questo problema: ti permettono di impacchettare le dipendenze necessarie all'applicazione in un ambiente isolato e riproducibile.

### Come funziona?
Nel pratico lo fanno utilizzando alcune funzionalità del kernel per isolare i processi e controllarne l'accesso alle risorse. Per citarne qualcuna:

- **Namespaces:** danno a un gruppo di processi una visione isolata delle risorse del sistema, es. un container può avere una propria interfaccia di rete e una propria visione dei processi in esecuzione.

- **Cgroups (control groups):** possono monitorare e limitare le risorse utilizzate dai processi, es. impedisci a un container di utilizzare più di 512 MB di RAM.

- **Capabilities:** permettono di limitare i privilegi dei processi, es. impedisci a un container di eseguire determinate operazioni amministrative.

Puoi creare ambienti isolati manualmente con degli strumenti Linux:

- **unshare:** ti permette di avviare processi con namespaces separati, quindi ognuno vede le sole risorse che è stato permesso di vedere.
- **chroot:** ti permette di modificare la directory visibile a un processo, gli fai vedere solo una porzione del filesystem come fosse la radice /.

### Strumenti per la gestione di container
Anziché creare e configurare manualmente ogni container, è conveniente utilizzare strumenti che automatizzano queste operazioni: 

- **Docker:** permette di creare immagini, eseguire container e gestirne il ciclo di vita.

- **Podman:** alternativa a Docker, funziona anche senza privilegi di root o demoni centrali attivi.

- **LXC:** permette di creare e gestire container che si comportano come sistemi Linux completi, con un proprio ambiente di sistema, servizi, utenti e processi; a differenza di Docker e Podman, non è focalizzato sull'esecuzione di una singola applicazione isolata.

### Che differenza fa con una macchina virtuale?
Riguarda il modo in cui viene virtualizzato il sistema:

- **Le macchine virtuali** utilizzano un hypervisor per virtualizzare l'hardware. Ogni VM esegue un proprio sistema operativo, con un kernel indipendente da quello dell'host.

- **I container** non virtualizzano l'hardware e non hanno bisogno di un proprio kernel. Isolano i processi utilizzando le funzionalità del kernel host, che viene condiviso tra i container.

I container sono più leggeri e veloci da avviare rispetto alle VM, perché non devono eseguire un sistema operativo completo. Le VM, offrono invece un isolamento più forte a livello di sistema operativo e permettono di eseguire sistemi operativi diversi sullo stesso host.

Un container deve essere compatibile con il kernel del sistema host: un container Linux necessita di un kernel Linux, un container Windows necessita di un kernel Windows. Per questo motivo, Docker su Windows usa una macchina virtuale Linux per eseguire container Linux.

---