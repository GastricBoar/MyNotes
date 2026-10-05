---
date: 2026-09-19
tags:
  - informatica
  - pubblico

---
# Disaster Recovery (DR)
---
Insieme di strategie e tecnologie utilizzate per ripristinare sistemi e dati informatici dopo un evento che ne compromette il funzionamento.

### Come funziona?
Un'organizzazione può subire eventi come un guasto hardware, un incendio, un attacco ransomware o un'interruzione di corrente. In questo contesto, il Disaster Recovery è un piano strutturato per ripristinare servizi e operatività.

Facendo un'esempio:

- Il server principale di un'azienda smetta improvvisamente di funzionare.

- L'azienda dispone di copie dei dati e configurazioni necessarie.

- Si attivano le procedure di Disaster Recovery.
  
- I sistemi vengono ripristinati utilizzando backup, sistemi ridondanti o un'infrastruttura alternativa.
  
- I servizi tornano progressivamente disponibili.

Due delle metriche utilizzate nei piani di Disaster Recovery sono:

- **RTO (Recovery Time Objective):** il tempo massimo entro cui un servizio deve essere ripristinato dopo un'interruzione, es. "il servizio deve essere ripristinato entro quattro ore dall'incidente".
  
- **RPO (Recovery Point Objective):** quantità massima di dati che l'organizzazione è disposta a perdere in un certo intervallo di tempo, es. "l'azienda deve essere preparata a perdere al massimo i dati prodotti nell'ultima ora".

Il Disaster Recovery non riguarda quindi soltanto i backup: comprende tutto ciò che serve a ripristinare l'operatività generale, quindi: backup regolari e conservati in diversi luoghi, infrastrutture ridondanti, siti di DR alternativi, procedure di ripristino documentate, test periodici del piano, RTO e RPO documentati.

---
[[Regola 3-2-1 di backup]]
[[Regola 3-2-1-1-0 di backup]]
[[Tipi di backup]]