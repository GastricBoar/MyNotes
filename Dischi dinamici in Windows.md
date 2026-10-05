---
date: 2026-04-05
tags:
  - informatica
  - pubblico

---
# Dischi dinamici in Windows
---
Un tipo di configurazione dischi su Windows, al posto delle partizioni tradizionali utilizza volumi dinamici.

Questa gestione flessibile dei dischi ti permette di unire, duplicare o distribuire dati tra più dischi, vediamo un paio di scenari.

### **Spanning**
Crei un unico spanned volume da più dischi, in questo modo:

1. hai un disco A da 500 GB che usi su server, ma finisce per riempirsi
2. colleghi al server un disco B da 250 GB
3. converti a disco dinamico entrambi
4. crei un volume spanned, quindi prendi disco A e disco B e li consolidi in un unico volume logico da 750 GB

Per vantaggio hai guadagnato spazio sul quale scrivere file, ma i contro sono due:

- **se uno dei due dischi si rompe, il volume diventa inutilizzabile:** un volume spanned distribuisce filesystem e dati su due dischi, se il disco B si rompe è certo che perderai i file salvati su disco B e quelli scritti "a cavallo" di disco A e disco B; i file scritti interamente su disco A potrebbero salvarsi in teoria, ma non è detto lo facciano sempre, il filesystem potrebbe esser stato corrotto
  
- **riconvertire a disco base richiede formattazione:** per migrare i dati su un nuovo server con dischi base dovresti copiare i dati su un altro supporto, formattare i dischi dinamici e ricopiare tutto con criterio

Come vedi è una misura di emergenza, è una toppa utile solo quando il beneficio immediato supera il rischio futuro, e comunque sai già che dovrai pianificare una migrazione.

### **Striping (o RAID 0)**
Crei un unico striped volume da più dischi, ogni tuo file viene distribuito (non replicato, attenzione) sui dischi.

Fare questo ti permette di scrivere file in parallelo, il guadagno è velocità di lettura e scrittura, ma se anche uno solo dei dischi si rompe avrai perso i dati di tutti i dischi dentro al [[RAID (Redundant Array of Independent Disks)]]; non è una possibilità come per lo spanning, è una certezza questa volta.

È molto pericoloso come vedi, per ogni disco che aggiungi stai moltiplicando la possibilità che qualcosa si rompa; è utile solo in contesti non critici o dove i dati sono già replicati altrove.

### **Mirroring (o RAID 1)**
Crei un volume mirrored da più dischi, ciascun file viene replicato sui dischi che compongono l'array.

Se uno dei dischi si rompe, hai tutti i file al sicuro sull'altro; di contro stai dimezzando la capacità dell'array.

### **RAID 5**
Crei un unico volume RAID 5 distribuendo dati e [[Parity]] su più dischi:

- ti servono almeno tre dischi (A, B e C)
- su dischi A e B ci metti i dati, su disco C ci metti la parità
- se si rompe A, usi B e la parità in C per ricostruirlo

Ti dà un compromesso tra tolleranza ai guasti e prestazioni: 

- sacrifica meno spazio di RAID 1, ma più di RAID 0
- è più veloce di RAID 1, ma meno di RAID 0
- la ricostruzione da parità stressa gli altri dischi, potrebbe farli guastare più velocemente

---
