---
date: 2026-09-13
tags:
  - informatica
  - pubblico

---
# Rainbow Table Attack
---
Attacco in cui l'attaccante utilizza una rainbow table per cercare di ricavare le password originali a partire da hash rubati.

### Come funziona?
Le rainbow tables sono database contenenti hash precalcolati di password comuni. Se l'attaccante riesce a intercettare l'hash della tua password, può confrontarlo con quelli presenti nella rainbow table per cercare di risalire alla password originale, senza dover calcolare ogni hash durante l'attacco in sè.

### Come si previene?
Il principale meccanismo contro le rainbow table è il salt: un valore casuale e diverso per ogni password, aggiunto prima di elaborare l'hash. Per fare un esempio:

- Mario sceglie la password "password123".
- Il software che gestisce l'autenticazione genera un salt tipo "x7LKp92"
- Combina la password con il salt, che diventa "password123x7LKp92".
- Il software calcola l'hash di quel nuovo valore combinato.
- Allo stesso tempo memorizza nome utente "Mario", salt "x7LKp92" e l'hash della password.
- Nel momento in cui Mario effettua nuovamente il login, il software recupera il salt associato al suo account e lo combina con la password inserita.
- Calcola nuovamente l'hash e lo confronta con quello memorizzato nel database.
- Se i due hash coincidono, la password inserita è corretta.

In questo modo la stessa password produce hash diversi e le rainbow tables precalcolate diventano molto meno efficaci.

---
[[Dictionary Attack]]