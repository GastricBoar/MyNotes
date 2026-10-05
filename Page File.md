---
date: 2026-02-25
tags:
  - informatica
  - pubblico

---
# Page File
---
In Windows, una porzione di spazio su disco che il sistema utilizza come "estensione" temporanea della [[RAM (Random Access Memory)]]; serve a gestire le situazioni in cui i programmi in esecuzione richiedono più memoria rispetto alla RAM fisica disponibile.

Per fare un esempio:

- Hai troppi programmi aperti e la RAM è piena.
  
- Interviene il kernel, invece che terminare il processo per Out-Of-Memory, identifica le pagine di memoria meno utilizzate e le sposta dalla RAM al page file su disco.
  
- Usa la RAM appena liberata per gestire i processi più usati.
  
- Se quei processi poco usati tornano a servire, li sposta di nuovo in RAM.


Non devi pensarla come "RAM aggiuntiva" (il page file è assai più lento della RAM) ma come un meccanismo di sicurezza temporaneo.

### **È davvero un file?**
Sì, è davvero un file formattato come page file, ma a differenza di altri file ci sta un trucco software di mezzo. Il [[Kernel]] fa questo:

1. Ottiene la mappatura dei blocchi fisici occupati dal file sul disco.
2. Bypassa il filesystem.
3. Utilizza direttamente quei blocchi grezzi per scrivere\leggere pagine di memoria della RAM.

### **Dove sta?**

Sta in `C:\pagefile.sys`

### **Il page file esiste in Linux?**
Sì, ma lì si chiama [[Swap]].

---
