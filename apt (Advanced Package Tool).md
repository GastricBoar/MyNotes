---
date: 2026-05-01
tags:
  - informatica
  - linux
  - pubblico

---
# apt (Advanced Package Tool)
---
Un package manager per distribuzioni [[Linux]] basate su Debian.

### Aggiornare l'elenco dei pacchetti  
  
Lanci il comando con la sintassi:  
  
```bash  
sudo apt update  
```  
  
Scarica l'elenco dei pacchetti disponibili dai repository configurati, senza installare alcun aggiornamento.  
  
### Aggiornare i pacchetti installati  
  
Lanci il comando con la sintassi:  
  
```bash  
sudo apt upgrade  
```  
  
Installa gli aggiornamenti disponibili per i pacchetti già installati.  
  
### Installare un pacchetto  
  
Lanci il comando con la sintassi `sudo apt install [pacchetto]`  
  
es.  
  
```bash  
sudo apt install git  
```  
  
### Rimuovere un pacchetto  
  
Lanci il comando con la sintassi `sudo apt remove [pacchetto]`  
  
es.  
  
```bash  
sudo apt remove git  
```  
  
### Rimuovere un pacchetto e i file di configurazione  
  
Lanci il comando con la sintassi `sudo apt purge [pacchetto]`  
  
es.  
  
```bash  
sudo apt purge git  
```  
  
### Rimuovere le dipendenze non più utilizzate  
  
Lanci il comando con la sintassi:  
  
```bash  
sudo apt autoremove  
```  
  
### Cercare un pacchetto  
  
Lanci il comando con la sintassi `apt search [nome]`  
  
es.  
  
```bash  
apt search firefox  
```  
  
### Visualizzare informazioni su un pacchetto  
  
Lanci il comando con la sintassi `apt show [pacchetto]`  
  
es.  
  
```bash  
apt show git  
```

---
