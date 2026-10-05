---
date: 2026-02-21
tags:
  - informatica
  - linux
  - pubblico

---
# paru
---
Wrapper di [[pacman]] per gestire pacchetti da repository ufficiali e [[AUR (Arch User Repository)]], semplificando installazione, ricerca e aggiornamento.

### Uso di base
Lanci il comando con la sintassi `paru [operazione] [opzioni] [pacchetto]`

### paru -S (sync/install)
Installa un pacchetto dai repository o AUR.

es. `paru -S firefox`

### paru -Syu
Aggiorna tutto il sistema (repo ufficiali + AUR).

- `S` → sync  
- `y` → aggiorna database  
- `u` → upgrade  

es. `paru -Syu`

### paru -Ss (search)
Cerca un pacchetto nei repository e AUR.

es. `paru -Ss nginx`

### paru -Qs (query search)
Cerca tra i pacchetti **già installati**.

- `Q` → query database locale  
- `s` → search  

es. `paru -Qs docker`


### paru -Q (query)
Mostra informazioni sui pacchetti installati.

es. `paru -Q`  
es. `paru -Qi nomepacchetto`


### paru -R (remove)
Disinstalla un pacchetto.

es. `paru -R nginx`


### paru -Rns
Disinstalla un pacchetto **con dipendenze inutilizzate e file di configurazione**.

- `n` → rimuove config  
- `s` → rimuove dipendenze non più necessarie  

es. `paru -Rns nginx`


### paru -Rnsdd
Forza la rimozione ignorando le dipendenze.

es. `paru -Rnsdd nomepacchetto`


### paru -U (upgrade da file)
Installa un pacchetto locale `.pkg.tar.zst`.

- NON scarica nulla da internet  
- usa un file già presente nel sistema  

es. `paru -U pacchetto.pkg.tar.zst`

### paru -Ql (list files)
Lista tutti i file installati da un pacchetto.

es. `paru -Ql nomepacchetto`

### paru -D (database)
Modifica informazioni del database locale (uso avanzato).

es. `paru -D --asdeps nomepacchetto`

---
