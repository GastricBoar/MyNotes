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

- **unshare:** ti permette di avviare processi con namespaces separati, quindi ognuno vede le sole risorse che gli sono state assegnate.
- **chroot:** ti permette modificare le directory visibili a un processo, gli fai vedere solo una porzione del filesystem come fosse la radice /.

### Strumenti per la gestione di container



---