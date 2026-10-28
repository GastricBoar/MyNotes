---
date: 2026-10-28-21-44
tags:
  - informatica
  - pubblico
---
# ssh (comando)
---
Comando Linux utilizzato per connettersi a sistemi remoti tramite protocollo SSH.

#### ssh-keygen -i (identity)
Specifica a quale chiave privata fare riferimento per autenticarsi su server remoto.

Lanci il comando con la sintassi `ssh -i [percorso chiave privata] [utente]@[host]`:

```bash
ssh -i ~/.ssh/id_ed25519 paolo@192.168.1.100
```

#### ssh-copy-id
Copia la chiave pubblica dal tuo PC al server remoto, aggiungendola al file `~/.ssh/authorized_keys` per l'utente specificato.

Lanci il comando con la sintassi `ssh-copy-id [utente]@[host]`:

```bash
ssh-copy-id paolo@192.168.1.100
```

#### ssh-keygen -t (type)
Genera una coppia di chiavi crittografiche utilizzando l'algoritmo che scegli.

Lanci il comando con la sintassi `ssh-keygen -t [algoritmo]`:

```bash
ssh-keygen -t ed25519
```

Qui ed25519 è un algoritmo di cifratura. La chiave privata rimane sul tuo computer (è lui che deve dimostrare la propria identità), mentre la chiave pubblica la installi sul server remoto al quale vuoi collegarti.

Durante la procedura puoi scegliere dove salvare le chiavi, per impostazione predefinita, le chiavi vengono salvate nella directory `~/.ssh/`: `id_ed25519` è la chiave privata, mentre `id_ed25519.pub` è la chiave pubblica.

Puoi anche scegliere di impostare una password che protegga la tua chiave, così se qualcuno te la ruba deve conoscere quella password per usarla.

---
[[SSH (Secure Shell)]]