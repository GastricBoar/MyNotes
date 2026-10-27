---
date: 2026-10-28-21-38
tags:
  - informatica
  - pubblico
---
# ssh-keygen
---
Comando Linux, genera e gestisce chiavi crittografiche per l'autenticazione SSH.

#### ssh-keygen -t ed25519
Genera una coppia di chiavi crittografiche utilizzando l'algoritmo Ed25519.

Lanci il comando con la sintassi `ssh-keygen -t [algoritmo]`:

```bash
ssh-keygen -t ed25519
```

La chiave privata rimane sul tuo computer (è lui che deve dimostrare la propria identità), mentre la chiave pubblica la installi sul server remoto al quale vuoi collegarti.

Durante la procedura puoi scegliere dove salvare le chiavi, per impostazione predefinita, le chiavi vengono salvate nella directory `~/.ssh/`: `id_ed25519` è la chiave privata, mentre `id_ed25519.pub` è la chiave pubblica.

Puoi anche scegliere di impostare una password che protegga la tua chiave, così se qualcuno te la ruba deve conoscere quella password per usarla.

---
[[ssh (comando)]]