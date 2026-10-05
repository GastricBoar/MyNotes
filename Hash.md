---
date: 2026-09-13
tags:
  - informatica
  - pubblico

---
# Hash
---
Funzione matematica che trasforma un dato di qualsiasi dimensione in una stringa, di lunghezza generalmente fissa, chiamata hash o digest.

### Come funziona?
Poter trasformare un certo dato in una stringa può essere utile in diversi contesti, ma prendiamone uno per esempio:

- Ti serve un modo per capire se un testo di 100 mila parole è stato modificato nel suo viaggio verso la consegna.
  
- Invece di confrontare direttamente tutto il contenuto, puoi far elaborare l'intero testo a un algoritmo di hashing, che calcola un valore chiamato hash e lo utilizza come una sorta di "impronta digitale" di quel contenuto. Un hash potrebbe assomigliare a "7f83b1657ff1fc53..." e tanto altro.

- Una volta arrivato, il destinatario può usare quello stesso algoritmo per calcolare l'hash del testo ricevuto e confrontarlo con quello originale; se i due hash coincidono, il contenuto non è cambiato; se sono diversi, significa che il contenuto è stato modificato.


Un hash è progettato per essere unidirezionale: è facile calcolarlo partendo dal dato originale, ma non dovrebbe invece essere possibile ricavare direttamente il dato originale partendo dall'hash.

Gli hash sono molto utili, per esempio:

- Verificare l'integrità dei file.
- Memorizzare le password in modo sicuro.
- Identificare dati o file.
- Verificare firme e certificati digitali.

### Tipi di algoritmi 
Esistono diversi algoritmi di hashing, progettati per scopi diversi:

- **MD5:** vecchio e non sicuro per usi crittografici.
- **SHA-1:** obsoleto e non sicuro contro collisioni.
- **SHA-2:** famiglia che include SHA-256 e SHA-512, ancora ampiamente utilizzata.
- **SHA-3:** famiglia più recente, alternativa a SHA-2.
- **bcrypt:** progettato specificamente per l'hashing delle password.
- **scrypt:** progettato per rendere più "costosi" gli attacchi con hardware specializzato.
- **Argon2:** moderno e pensato per il password hashing, progettato per essere resistente agli attacchi con GPU.

---
[[Rainbow Table Attack]]