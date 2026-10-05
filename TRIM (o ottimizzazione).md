---
date: 2026-04-06
tags:
  - informatica
  - pubblico

---
# TRIM (o ottimizzazione)
---
Il comando con cui il [[Sistema operativo]] segnala all'[[SSD (Solid State Drive)]] quali dati non sono più utilizzati.

### Il contesto
Come visto nella pagina dedicata, su un SSD:

- i dati si scrivono a livello pagina, ma si cancellano solo a livello blocco
- se vuoi eliminare solo 100 pagine da un blocco, devi eliminare il blocco per intero
- quando elimini un file, non lo rimuovi fisicamente dall'SSD
- lo stai rimuovendo a livello logico dal [[Filesystem]]
- l'SSD non sa che quei dati sono da rimuovere
- Nel tempo le pagine inutilizzate si accumulano, e diventa un problema (leggi sotto)
  
<img src="Utilities/Media/Pasted%20image%2020260411175615.png" alt="Pasted image 20260411175615.png" width="337">

### Come fa a sapere cosa eliminare allora?
Tramite TRIM, nello specifico:

- il sistema operativo invia all'SSD una lista di indirizzi logici ([[LBA (Logical Block Addressing)]] non più in uso
- il controller dell'SSD marca quelle pagine come "invalide"

### E poi il TRIM li elimina?
No, TRIM non elimina i dati dai blocchi; se ne occupa un altro processo, la [[Garbage collection]]:

- itera su ciascun blocco
- sposta le pagine valide in un altro blocco vuoto
- ignora le pagine marcate "invalide" dal TRIM, restano dove sono
- elimina il contenuto del blocco
- adesso hai un blocco vuoto pronto a essere utilizzato, e le pagine valide in un altro blocco; fine!

Tornando al perchè la garbage collection senza TRIM sia un problema: 

- se l'SSD non sa quali dati sono ancora validi e quali no, copia tutto senza scrupoli
- la garbage collection cerca di liberare blocchi, nel farlo legge e scrive più del necessario
- si chiama write amplification, e usura le celle NAND inutilmente

### Come si usa TRIM?
Per la maggior parte non lo lanceresti manualmente: il sistema operativo lo usa quando elimini file, svuoti il cestino o fai cose che al file system suggerisca "ci sono dei dati da rivedere".

Può anche accadere periodicamente con una certa frequenza, e se (su Windows) apri il menù contestuale del disco e fai click su "Ottimizza" allora eseguirà TRIM e altre piccole operazioni di ottimizzazione.

---
