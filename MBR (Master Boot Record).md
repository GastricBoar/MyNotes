---
date: 2026-03-02
tags:
  - informatica
  - pubblico

---
# MBR (Master Boot Record)  
---  
Uno schema di partizionamento che combina tabella delle partizioni e codice di bootstrap nel primo settore del disco.  
  
Tu hai il sistema operativo sul tuo dispositivo di archiviazione, ma il tuo PC deve trovare un modo per puntare a quel sistema operativo quando lo accendi al mattino. Serve quindi un punto iniziale da cui partire per trovare il sistema operativo; pensala come "il vinile deve girare per riprodurre le canzoni, ma dove poggio la testina?"  
  
### Dove sta l'MBR?  
Il punto di partenza è il LBA 0 (Logical Block Address 0), il primissimo settore di un dispositivo di archiviazione.  
  
Quando il computer si accende, il [[BIOS]] legge questo settore per capire come è organizzato il disco e da dove iniziare il processo di avvio.  
  
### Cosa contiene?  
Due cose importanti:  
  
- la tabella delle partizioni: descrive come il disco è organizzato  
- il codice di bootstrap: che avvia il processo di boot  
  
### I limiti: le partizioni primarie  
La tabella delle partizioni ti permette di creare fino a quattro partizioni primarie sul disco.  
  
Quattro partizioni non sono tantissime, ma negli anni '80 non si pensava "hurr durr devo creare una partizione per il gaming, una per i documenti e una per le foto". Piuttosto si pensava "su una partizione ci metto DOS, su un'altra UNIX, su un'altra CP/M etc." per darti la possibilità di avviare sistemi operativi diversi a seconda delle necessità.  
  
Con il progredire dei sistemi operativi il limite è diventato più evidente: già solo Windows ti crea una partizione di sistema, una partizione di recovery e altre piccole partizioni di servizio al bisogno, il che ti lascia meno spazio per creare partizioni aggiuntive a scopo organizzativo.  

Il limite delle quattro partizioni riguarda solo le partizioni primarie. Per superarlo puoi usare una partizione estesa, che funziona come un contenitore dentro il quale è possibile creare più partizioni dette "logiche". 

### I limiti: la dimensione delle partizioni 
  
MBR permette di creare partizioni con dimensione massima di circa 2 TB. Quando è stato progettato, questo limite sembrava praticamente irraggiungibile.  
  
### Come avviene l'avvio del sistema operativo?  
Tramite il codice di bootstrap contenuto nell’MBR.  
  
Questo codice:  
  
1. legge la tabella delle partizioni  
2. cerca quella contrassegnata come partizione attiva    
3. passa il controllo al bootloader presente in quella partizione  
  
Il bootloader poi carica il sistema operativo vero e proprio. 
  
---