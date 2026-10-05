---
date: 2026-07-06
tags:
  - informatica
  - pubblico

---
# CMD (Command Prompt)
---
Un'interfaccia a riga di comando (CLI) sviluppata da Microsoft negli anni '80.  
  
È il discendente diretto di MS-DOS, è oggi mantenuta per motivi di retrocompatibilità, ma è stata in gran parte sostituita da [[Powershell]].  
  
### In che modo è diverso da Powershell?  
Per un paio di motivi:  
  
- **Lavora solo con testo:** se chiedi una lista di processi aperti, ti restituisce una tabella di testo da filtrare in vari modi; Powershell visualizza invece degli oggetti, che sono ordinabili in maniera dinamica (es. ordina per quale processo usa più memoria).  
  
- **Utilizza comandi nativi DOS:** come `dir`, `cd` o `copy`; Powershell utilizza i Cmdlet (command-let), che seguono una struttura verbo-sostantivo es. `Get-ChildItem`, `Stop-Process` o `Get-Service`  
  
- **Ha accesso limitato alle impostazioni di sistema**: le più profonde, mentre Powershell può accedere senza problemi a registro di sistema, servizi di rete, certificati di sicurezza, API e database.  
  
- **Non è cross-platform:** opera solo su Windows, mentre Powershell è diventato open-source e lavora su Windows, Linux e macOS con gli stessi identici comandi.  
  
- **I suoi script hanno estensione diversa:** utilizzano estensione .bat, mentre Powershell utilizza estensione .ps1  

---