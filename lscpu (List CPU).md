---
date: 2026-07-06
tags:
  - informatica
  - linux
  - pubblico

---
# lscpu (List CPU)  
Comando [[Linux]] utilizzato per visualizzare informazioni su architettura e caratteristiche della CPU.
  
Le informazioni vengono recuperate dal kernel e dal filesystem `/proc`.  
  
### Visualizzare le informazioni della CPU  
Lanci il comando con la sintassi:  
  
```bash  
lscpu  
```  
  
Mostra informazioni come:  
  
- architettura della CPU;  
- numero di CPU logiche;  
- numero di core e socket;  
- thread per core;  
- modello del processore;  
- frequenza della CPU;  
- cache L1, L2 e L3;  
- supporto alla virtualizzazione.  
  
### lscpu -e (Extended)  
  
Visualizza le informazioni sulle singole CPU logiche in formato tabellare.  
  
Lanci il comando con la sintassi:  
  
```bash  
lscpu -e  
```

---