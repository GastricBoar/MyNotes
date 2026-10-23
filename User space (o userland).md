---
date: 2026-10-24-16-32
tags:
  - informatica
  - linux
  - pubblico
---
# User space (o userland)
---
Ambiente del sistema operativo in cui vengono eseguiti programmi e servizi che non fanno parte del kernel.

### La storia
Nei primi sistemi informatici, i programmi avevano accesso diretto a memoria e hardware, senza una separazione rigorosa tra il codice applicativo e quello di sistema; significa che un programma poteva interferire con il funzionamento degli altri o compromettere l'intero sistema.

È un grosso rischio di sicurezza, e nel tempo è cresciuta sempre più la necessità di separare il codice a privilegi elevati da quello a privilegi limitati.

In questo discorso:

- Il kernel è il componente privilegiato che gestisce le risorse di sistema, come memoria, processore e dispositivi hardware.
  
- I normali programmi vengono eseguiti in uno spazio isolato, lo user space.
  
### Come funziona?
I programmi dello user space non possono accedere liberamente alle risorse protette:

- Se un programma deve svolgere un'operazione riservata al kernel, ricorre a una system call, un meccanismo che consente di richiedere al kernel operazioni privilegiate.
  
- La CPU trasferisce il controllo al kernel.
  
- Il kernel verifica le autorizzazioni necessarie ed esegue l'operazione richiesta, restituendo il risultato al programma.

Questa separazione è vantaggiosa per diversi motivi:

- Impedisce ai programmi di accedere liberamente alle risorse più delicate.

- Limita gli effetti dei malfunzionamenti dei singoli programmi e permette al sistema operativo di gestirne le risorse. 

---
[[Kernel]]
[[Sistema operativo]]
