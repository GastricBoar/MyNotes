---
date: 2026-11-04-20-30
tags:
  - informatica
  - linux
  - pubblico
---
# SELinux
---
Un sistema di sicurezza Linux sviluppato da Red Hat Enterprise Linux, applica regole che limitano ciò che processi, utenti e applicazioni possono fare.

### Il contesto
I permessi tradizionali di Linux (proprietario, gruppo, altri) sono basati sul modello DAC (Discretionary Access Control), si chiama così perchè una risorsa è accessibile "a discrezione del proprietario". Questi permessi non sono sempre sufficienti a controllare l'accesso alle risorse. Per esempio, immagina questo:

- Un web server Nginx viene compromesso da un attaccante.
- Il processo di Nginx ha una serie di privilegi: può leggere i file del sito web, gestire richieste HTTP, accedere alle porte di rete necessarie, scrivere nei propri log etc.
- Non dovrebbe invece avere bisogno di leggere file contenenti password, chiavi SSH o configurazioni di altri servizi in giro per il sistema.
- L'attaccante potrebbe sfruttare una vulnerabilità di Nginx ed eseguire comandi sul server attraverso di esso.

Ecco, è in questo contesto che SELinux ti permette di limitare preventivamente ciò che Nginx può fare, a prescindere dai normali permessi Unix.

### Come funziona?
I permessi tradizionali Linux sono basati sul modello DAC, ma SELinux basa l'accesso alle risorse su un modello chiamato MAC (Mandatory Access Control): non dipendono dal proprietario, ma sono obbligate da policy di sicurezza a livello sistema e non modificabili liberamente dagli utenti.

Funziona così: SELinux assegna delle etichette (dette security contexts) a oggetti del sistema come processi, file, directory, porte di rete e utenti. Da lì le policy SELinux stabiliscono quali operazioni sono consentite tra questi oggetti. 

Per esempio: il processo Nginx può leggere i contenuti web autorizzati, ma non può accedere ai file di sistema; è questione di limitare i danni.

Un oggetto deve rispettare sia i permessi DAC che le policy MAC, è un livello ulteriore di controllo: anche se un processo viene compromesso, SELinux gli impedisce di accedere a risorse non autorizzate.

A differenza di RHEL, Ubuntu adotta il MAC tramite il sistema AppArmor, attivo per impostazione predefinita.

### Le modalità di SELinux
SELinux può funzionare in tre modalità:

- **Enforcing:** applica (to enforce) le policy e blocca le operazioni non autorizzate.
- **Permissive:** non blocca operazioni, registra solo le violazioni.
- **Disabled:** del tutto disabilitato.

Su RHEL, SELinux è normalmente abilitato in modalità Enforcing, puoi verificarne lo stato con il comando `getenforce`.

---
[[Permessi in Linux]]