---
date: 2026-09-14
tags:
  - informatica
  - pubblico

---
# Rootkit
---
Malware progettato per ottenere e mantenere un accesso privilegiato a un dispositivo, cercando allo stesso tempo di nascondere la propria presenza.

### Come funziona?
Immagina che un attaccante voglia prendere il controllo di un computer:

- Prima deve riuscire a compromettere il dispositivo, per esempio sfruttando una vulnerabilità, utilizzando credenziali rubate o facendo eseguire alla vittima un altro malware.

- Una volta ottenuti privilegi sufficienti, può installare un rootkit nel sistema.

- Il rootkit modifica o sfrutta componenti del sistema operativo per nascondere la propria presenza; può nascondere file, processi, connessioni di rete o altre attività malevole.

L'attaccante può quindi mantenere l'accesso al dispositivo per un lungo periodo, ed è proprio la capacità di nascondersi nel sistema a rendere i rootkit insidiosi.

### Come si previene?
La difesa principale consiste nel rendere più difficile la compromissione iniziale e impedire che un attaccante possa ottenere facilmente privilegi elevati:

- Mantieni sistema operativo e applicazioni aggiornati.

- Utilizza account con privilegi limitati.

- Utilizza antivirus/EDR.

- Evita software e file di provenienza dubbia.

- Utilizza secure boot quando disponibile.

---
[[Trojan]]
[[Worm]]

