---
date: 2026-07-06
tags:
  - informatica
  - pubblico

---
# Powershell  
---  
Un'interfaccia a riga di comando (CLI) e linguaggio di scripting avanzato sviluppato da Microsoft nel 2006.  
  
Basato sul framework .NET, è nato per superare i limiti dell'amministrazione di sistema tradizionale e ha in gran parte sostituito il vecchio [[CMD (Command Prompt)]].  
  
### In che modo è diverso da CMD?  
Per un paio di motivi:  
  
- **Lavora con gli oggetti:** se chiedi una lista di processi aperti, non restituisce semplice testo ma elementi intelligenti ordinabili e filtrabili in maniera dinamica (es. ordina per quale processo usa più memoria); CMD visualizza invece una tabella di puro testo.  
  
- **Utilizza i Cmdlet (command-let):** comandi che seguono una struttura logica verbo-sostantivo, come `Get-ChildItem`, `Stop-Process` o `Get-Service`; CMD utilizza invece i vecchi comandi nativi DOS come `dir`, `cd` o `copy`.  
  
- **Ha accesso totale alle impostazioni di sistema:** incluse le più profonde, permettendo di gestire senza problemi registro di sistema, servizi di rete, certificati di sicurezza, API e database; CMD ha invece un accesso limitato.  
  
- **È cross-platform:** è diventato open-source e lavora nativamente su Windows, Linux e macOS con gli stessi identici comandi, mentre CMD opera esclusivamente su Windows.  
  
- **I suoi script hanno estensione diversa:** utilizzano estensione .ps1, mentre CMD utilizza estensione .bat  
  
---