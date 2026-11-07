---
date: 2026-11-08-23-28
tags:
  - informatica
  - linux
  - pubblico
---
# vmstat (Virtual Memory Statistics)
---
Comando Linux utilizzato per monitorare le prestazioni del sistema, mostrando statistiche su processi, memoria, swap, I/O e CPU.

#### vmstat
Fotografia sintetica dello stato delle risorse del sistema.

L'output si divide in categorie:

- `procs`: processi in esecuzione (`r`) e in stato di attesa (`b`).
- `memory`: memoria libera, buffer e cache.
- `swap`: memoria trasferita da e verso lo swap (`si`, `so`).
- `io`: blocchi letti (`bi`) e scritti (`bo`).
- `system`: interrupt (`in`) e context switch (`cs`).
- `cpu`: tempo CPU dedicato a user (`us`), system (`sy`), idle (`id`) e altri stati.

#### vmstat {intervallo} {numero}
Esegue rilevazioni periodiche, specificando l'intervallo tra una rilevazione e l'altra e il numero totale di rilevazioni.

Lanci il comando con la sintassi `vmstat [intervallo] [numero]`:

```
vmstat 2 5
```

Una rilevazione ogni 2 secondi, 5 rivelazioni in totale.

#### vmstat -s (statistics)
Mostra un riepilogo delle statistiche relative alla memoria e ad altre risorse del sistema.

Lanci il comando con la sintassi `vmstat -s`:

```
vmstat -s
```

---
[[top (top processes)]]