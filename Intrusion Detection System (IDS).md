---
date: 2026-09-08
tags:
  - informatica
  - pubblico

---
# Intrusion Detection System (IDS)
---
Sistema di sicurezza che monitora traffico di rete o le attività di un dispositivo per individuare possibili attacchi informatici.

### Come funziona?
All'interno di una rete possono verificarsi attività malevole non necessariamente bloccabili da un firewall, es. un attaccante potrebbe riuscire a sfruttare una vulnerabilità o credenziali rubate.

Un IDS monitora traffico o attività del sistema per poi confrontare con regole, attacchi conosciuti e comportamenti considerati anomali; lo scopo è riconoscere attività che potrebbero indicare un'intrusione. Per esempio:

- Un IDS di rete rileva un numero elevato di richieste sospette provenienti dallo stesso indirizzo IP.

- Confronta il traffico con  regole o firme di attacchi conosciuti.

- Rileva un comportamento compatibile con un attacco.

- Genera un avviso che può essere analizzato dall'amministratore o da un altro sistema di sicurezza.

È principalmente uno strumento di rilevamento: individua la possibile minaccia e segnala l'evento, ma normalmente non interviene per bloccarla direttamente.

Nel pratico, può essere un software installato su server, installato su una macchina dedicata, o parte di un apparato di rete.

### Tipi di IDS
Classificati in base a ciò che monitorano:

- **NIDS (Network-based IDS)**: monitora l'intero traffico di rete.

- **HIDS (Host-based IDS)**: monitora un singolo dispositivo, analizza attività come modifiche ai file, processi o log di sistema.

### In che modo è diverso da un IPS?
È diverso in quello che succede dopo aver rilevato la minaccia: se l'IDS rileva e segnala l'attività sospetta, l'IPS può sia rilevarla che intervenire automaticamente per bloccarla.

---
[[Intrusion Prevention System (IPS)]]