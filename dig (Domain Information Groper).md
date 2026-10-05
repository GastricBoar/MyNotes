---
date: 2026-05-12
tags:
  - informatica
  - linux
  - pubblico

---
# dig (Domain Information Groper)
---
Comando [[Linux]] utilizzato per interrogare i server DNS e ottenere informazioni sulla risoluzione dei nomi di dominio.  

Lo puoi usare per diagnosticare problemi DNS.  
  
### Eseguire una query DNS  
Lanci il comando con la sintassi `dig [dominio]`  
  
es.  
  
```bash  
dig google.com  
```  
  
Visualizza informazioni come l'indirizzo IP associato al dominio, il server DNS interrogato e il tempo di risposta.  
  
### Interrogare un server DNS specifico  
Lanci il comando con la sintassi `dig @[server DNS] [dominio]`  
  
es.  
  
```bash  
dig @8.8.8.8 google.com  
```  
  
### dig +short (Short)  
Mostra solo la risposta essenziale della query.  
  
Lanci il comando con la sintassi:  
  
```bash  
dig +short google.com  
```  
  
### dig MX (Mail Exchange)  
Visualizza i record MX del dominio.  
  
Lanci il comando con la sintassi:  
  
```bash  
dig google.com MX  
```  
  
### dig NS (Name Server)  
Visualizza i name server autorevoli del dominio.  
  
Lanci il comando con la sintassi:  
  
```bash  
dig google.com NS  
```  
  
### dig A (Address)  
Visualizza i record IPv4 del dominio.  
  
Lanci il comando con la sintassi:  
  
```bash  
dig google.com A  
```  
  
### dig AAAA (Quad A)  
Visualizza i record IPv6 del dominio.  
  
Lanci il comando con la sintassi:  
  
```bash  
dig google.com AAAA  
```

---
