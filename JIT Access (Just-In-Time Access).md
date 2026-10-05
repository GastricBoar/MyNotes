---
date: 2026-08-30
tags:
  - informatica
  - pubblico

---
# JIT Access (Just-In-Time Access)
---
Modello di gestione degli accessi in cui i permessi vengono concessi all'utente solo quando necessari e per il tempo necessario, invece di essere assegnati permanentemente.

### Come funziona?
L'applicazione pratica di JIT cambia un po' a seconda del sistema che stai utilizzando, ma l'idea è sempre "normalmente non hai un certo privilegio > lo attivi > scade".

Si potrebbero fare tanti esempi: l'aggiunta temporanea a Administrators su un server, privilegi elevati temporanei su un database, il `sudo` su Linux, un ruolo amministrativo temporaneo in Kubernetes. Adesso per dirne una, mettiamo tu stia utilizzando Google Cloud e voglia applicare JIT alle macchine virtuali:

- Configuri l'accesso IAM in modo che l'utente possa attivare temporaneamente il ruolo `Compute Admin`, invece di averlo assegnato permanentemente.
  
- L'utente, quando deve modificare una macchina virtuale, richiede l'attivazione del ruolo.
  
- Il sistema concede temporaneamente i privilegi amministrativi per un certo periodo stabilito.
  
- L'utente effettua le modifiche necessarie.
  
- Alla scadenza del periodo, il ruolo viene automaticamente disattivato e l'utente torna a non avere quei privilegi.

L'obiettivo è ridurre i privilegi permanenti e quindi limitare i danni che potrebbero derivare dalla compromissione di un account privilegiato; è una buona continuazione del principio del minimo privilegio.

### Cosa è JEA?
Se JIT stabilisce quando un utente può ottenere un privilegio, JEA (Just Enough Administration) stabilisce invece quali operazioni può effettuare con quel privilegio.

---