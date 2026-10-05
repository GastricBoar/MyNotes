---
date: 2026-07-01
tags:
  - informatica
  - linux
  - pubblico

---
# mtr (My Traceroute)
---
Comando [[Linux]] utilizzato per analizzare il percorso verso un host combinando le funzionalità di `ping` e `traceroute`.  
  
È un'alternativa moderna a `traceroute`, perchè aggiorna continuamente le statistiche di rete, mostrando in tempo reale latenza e perdita di pacchetti per ogni hop.
  
### Avviare un'analisi  
Lanci il comando con la sintassi `mtr [host]`  
  
es.  
  
```bash  
mtr google.com  
```  
  
### mtr -n (Numeric)  
Mostra gli indirizzi IP senza eseguire la risoluzione DNS.  
  
Lanci il comando con la sintassi:  
  
```bash  
mtr -n google.com  
```  
  
### mtr -r (Report)  
Esegue un numero limitato di test e restituisce un report finale, invece della modalità interattiva.  
  
Lanci il comando con la sintassi:  
  
```bash  
mtr -r google.com  
```  
  
### mtr -c (Count)  
Specifica il numero di pacchetti da inviare.  
  
Lanci il comando con la sintassi:  
  
```bash  
mtr -c 10 google.com  
```  
  
### mtr -w (Wide Report)  
Visualizza un report con colonne più larghe, evitando il troncamento dei nomi host.  
  
Lanci il comando con la sintassi:  
  
```bash  
mtr -rw google.com  
```  

---
[[traceroute]]