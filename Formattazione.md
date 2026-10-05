---
date: 2026-03-16
tags:
  - informatica
  - pubblico

---
# Formattazione
---
Il processo con cui si crea (o ripristina) e inizializza un [[Filesystem]] su un disco o partizione, rendendolo utilizzabile dal [[Sistema operativo]]. È una cosa che fai quando colleghi un disco per la prima volta al PC, o quando vuoi ricominciare da zero dopo del tempo.

### **Cosa succede durante la formattazione?**
Un paio di cose, e dipende anche da quale file system usi:

1. **Crea il filesystem:** si sceglie il filesystem da utilizzare e i suoi parametri (es. "quanto son grandi i [cluster](obsidian://open?vault=la%20baracchina&file=Atlas%2FCluster%20nei%20filesystem)?)
   
2. **Divide lo spazio in cluster:** effettivamente.
   
3. **Crea le strutture logiche del filesystem:** a ognuno la sua, ma se prendiamo FAT come esempio troviamo boot sector, FAT, directory e l'area dati.
   
4. **Marcatura dei cluster:** non vengono scritti davvero come si fa con i file, vengono marcati come liberi nel senso di "scrivibili dal sistema operativo".
   
5. **(Opzionale) marcatura dei cluster danneggiati:** un cluster può esser danneggiato a prescindere dal fatto che il disco sia nuovo o usato, è fisiologico. Il file system non li può riparare; quello che può invece fare è marcarli come danneggiati, come stesse mettendo attorno un cono arancione di pericolo. Il valore con il quale li marca cambia a seconda del filesystem, ma per una tabella FAT16 è "FFF7" per dirne uno.

### **Il quick format**
Il quick format crea il file system e marca i cluster come liberi. 

Il passaggio "marca i cluster come liberi" è da capire, perchè se i cluster avevano sopra dei dati, resteranno lì fino a quando non saranno sovrascritti da altro. L'esser marcati come liberi significa "il sistema operativo può scrivere in questo punto", ma i dati son lì ed è questo il principio alla base dei software che recuperano dati anche quando li hai cancellati lato OS.

Non controlla settori danneggiati, non sovrascrive i dati, ed è per questo molto veloce. È questa la scelta comune quando hai davanti un disco sano e non ti interessa cancellare i dati in modo sicuro: prepari un disco personale, formatti una chiavetta USB etc.

### **Il full format**
**Il full format** è più lento del quick format, fa tutto quello che fa il quick format ma controlla anche settori danneggiati e sovrascrive i dati.

"Sovrascrive i dati" nel senso che prende ogni cluster (occupato o meno che sia) e ci scrive sopra degli zeri, eliminando di fatto i dati precedenti.

Userai il full format se:
- hai davanti un disco vecchio o sospetto e vuoi verificare non ci siano settori danneggiati
- stai cancellando dati sensibili prima di vendere
- hai notato file corrotti ed errori del filesystem

---
