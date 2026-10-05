---
date: 2026-04-28
tags:
  - informatica
  - linux
  - pubblico

---
# fsck (filesystem check)  
---  
Un comando [[Linux]] utilizzato per verificare l'integrità del [[Filesystem]] e ripararne errori.
  
### Uso di base  
Lanci il comando con la sintassi fsck [dispositivo]  

es. `fsck /dev/sda1`

Devi assolutamente ricordare che il comando fsck lo esegui solo a filesystem smontato: lanciarlo a filesystem montato è un problema, sarebbe come operare un paziente mentre corre una maratona; i dati vengono scritti in continuazione, e spostare cose avanti e dietro potrebbe corromperli.

Adesso, facciamo tre esempi per capire:

- Riparare una chiavetta USB o un disco esterno: smonti il volume da filesystem con qualcosa tipo `umount /dev/sdb1`, e poi lanci fsck.
  
- Riparare una partizione secondaria: smonti il volume e poi lanci fsck.
  
- Riparare la partizione root/primaria: ecco, qui non puoi smontare il volume da filesystem mentre lo usi, quindi o prendi una live USB e lo smonti dall'esterno per poi lanciare fsck, oppure chiedi a Linux di riparare il filesystem prima dell'avvio (se ti interessa, cercati come farlo).
### fsck -y (yes)
Risponde automaticamente sì a tutte le domande di riparazione, così da garantirti esecuzione non interattiva.

es. `fsck -y /dev/sdb3`

### Come funziona?
Fa una serie di verifiche su filesystem, tra cui: controlla l'integrità degli [[inode (index node)]], valida la gerarchia delle directory, ricollega i percorsi orfani, verifica la coerenza dei riferimenti ai file e sincronizza il conteggio finale dello spazio libero e usato.


---
[[mount (mount filesystem)]]