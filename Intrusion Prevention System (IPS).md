---
date: 2026-09-08
tags:
  - informatica
  - pubblico

---
# Intrusion Prevention System (IPS)
---
Sistema di sicurezza che monitora il traffico di rete o le attività di un dispositivo per individuare e bloccare automaticamente possibili attacchi informatici.

### Come funziona?
Un IPS analizza il traffico o le attività del sistema e le confronta con regole, firme di attacchi conosciuti e comportamenti considerati anomali.

Quando identifica un'attività malevola può intervenire direttamente per bloccarla.

Per esempio:

- Un attaccante invia una serie di richieste che corrispondono alla firma di un attacco conosciuto.
- L'IPS analizza il traffico e identifica il comportamento come malevolo.
- Blocca le richieste o la connessione dell'attaccante, o può generare un avviso per informare l'amministratore dell'evento.

Nel pratico, può essere un software installato su un server, eseguito su una macchina dedicata o integrato in un apparato di rete.

### Tipi di IPS
Possono essere classificati in base a ciò che monitorano:

- **NIPS (Network-based IPS)**: monitora il traffico di rete e può bloccare attività malevole dirette verso i sistemi al suo interno.
  
- **HIPS (Host-based IPS)**: monitora un singolo dispositivo e può bloccare attività sospette, come modifiche non autorizzate ai file o l'esecuzione di processi malevoli.

### In che modo è diverso da un IDS?
La differenza principale è ciò che succede dopo aver rilevato la minaccia: l'IDS rileva e segnala l'attività sospetta, mentre l'IPS può sia rilevarla che intervenire automaticamente per bloccarla.

---
[[Intrusion Detection System (IDS)]]