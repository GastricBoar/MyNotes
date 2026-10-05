---
date: 2026-07-01
tags:
  - informatica
  - linux
  - pubblico

---
# traceroute
---
Comando [[Linux]] utilizzato per tracciare il percorso che i pacchetti seguono per raggiungere un host di destinazione.  
  
Mostra tutti gli hop (router) attraversati e il tempo impiegato per raggiungere ciascuno di essi.
  
### Tracciare il percorso verso un host  
Lanci il comando con la sintassi `traceroute [host]`  
  
es.  
  
```bash  
traceroute google.com  
```  
  
### traceroute -n (Numeric)  
  
Mostra gli indirizzi IP senza eseguire la risoluzione DNS dei nomi host.  
  
Lanci il comando con la sintassi:  
  
```bash  
traceroute -n google.com  
```  
  
### traceroute -m (Max TTL)  
  
Specifica il numero massimo di hop da attraversare.  
  
Lanci il comando con la sintassi:  
  
```bash  
traceroute -m 20 google.com  
```  
  
### traceroute -w (Wait Time)  
  
Specifica il tempo massimo di attesa per una risposta, espresso in secondi.  
  
Lanci il comando con la sintassi:  
  
```bash  
traceroute -w 2 google.com  
```

---