---
date: 2026-02-03
tags:
  - informatica
  - pubblico

---
# Sistema operativo
---
Il sistema operativo è l’insieme di software che, utilizzando i meccanismi forniti dal Kernel, organizza l’ambiente in cui i processi vengono eseguiti.

### Ma che significa? non è la stessa cosa che fa il kernel?
Questa definizione qui è un po' astratta e potrebbe sembrare si sovrapponga con quella del kernel. È destinato ad essere così, perchè sia il kernel che il sistema operativo definiscono o regolano il modo in cui le risorse accedono all'hardware, ma a livello concettuale lo fanno in maniera diversa.

Quelle del sistema operativo sono politiche organizzative di alto livello, mentre quelli del kernel sono meccanismi tecnici più bassi.

Il sistema operativo (userland, servizi, configurazioni) stabilisce chi può fare cosa, con che priorità e in che ordine.

Il kernel invece esegue, sospende, isola, protegge processi usando l'hardware.

| Aspetto          | Sistema operativo                             | Kernel                             |
| ---------------- | --------------------------------------------- | ---------------------------------- |
| Ruolo generale   | organizza l'ambiente di esecuzione            | fornisce le astrazioni hardware    |
| Tipo di scelte   | decide chi, quando, con che priorità          | decide come tecnicamente           |
| Livello          | alto (userland, servizi, config)              | basso (codice privilegiato)        |
| Processi         | stabilisce priorità, limiti, gruppi           | crea, distrugge, sospende          |
| Esempio processi | "browser in foreground, backup in background" | `fork()`, `exec()`, context switch |
| CPU              | definisce politiche di scheduling             | assegna la CPU e gestisce timer    |
| Esempio CPU      | "app interattiva più reattiva"                | interrupt, preemption              |
| Memoria          | impone limiti e quote                         | alloca, protegge, isola            |
| Esempio memoria  | "max 1 GB per questo servizio"                | paging, MMU, segfault              |
| File system      | definisce permessi e struttura                | I/O su disco, cache                |
| Esempio file     | "solo root scrive in `/etc`"                  | verifica UID/GID                   |
| Dispositivi      | decide chi può usare cosa                     | driver e accesso hardware          |
| Esempio device   | "questa app non usa la webcam"                | blocco a livello driver            |

---
[[Kernel]]