---
date: 2026-09-14
tags:
  - informatica
  - pubblico

---
# Worm
------
Malware progettato per replicarsi autonomamente da un dispositivo all'altro, generalmente sfruttando una rete.

### Come funziona?
Immagina una rete aziendale con decine di computer collegati tra loro:

- Uno solo dei computer viene infettato da un worm, magari ha sfruttato una vulnerabilità, magari ci è arrivato tramite mail o tramite internet.
  
- Da lì può cercare autonomamente altri dispositivi vulnerabili presenti sulla rete e tentare di infettarli; nel giro di poco tempo si è diffuso in gran parte della rete.

A differenza di molti altri malware, il worm non ha necessariamente bisogno che l'utente apra un file o esegua un programma per continuare a diffondersi.

### In che modo è diverso da un virus?
La differenza principale riguarda il modo in cui si diffondono: un virus normalmente ha bisogno di essere associato a un file o programma eseguito, mentre un worm è progettato per diffondersi autonomamente senza richiedere necessariamente l'interazione dell'utente.

### Come si previene?
La difesa principale consiste nel ridurre le vulnerabilità che il worm potrebbe sfruttare e limitare la possibilità che un dispositivo infetto raggiunga gli altri dispositivi della rete:

- Mantieni sistemi operativi e applicazioni aggiornati.
- Utilizza firewall e sistemi di sicurezza di rete.
- Segmenta la rete per limitare la propagazione tra dispositivi.
- Utilizza antivirus/EDR per rilevare il malware.
- Monitora il traffico di rete per individuare attività anomale.

---
[[Trojan]]
[[Rootkit]]