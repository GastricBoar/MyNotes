---
date: 2026-02-25
tags:
  - informatica
  - linux
  - pubblico

---
# Swap
---
In Linux, una porzione di spazio su disco che il sistema utilizza come "estensione" temporanea della [[RAM (Random Access Memory)]]; serve a gestire le situazioni in cui i programmi in esecuzione richiedono più memoria rispetto alla RAM fisica disponibile.

Per fare un esempio:

- Hai troppi programmi aperti e la RAM è piena.
  
- Interviene il kernel, invece che terminare il processo per Out-Of-Memory, identifica le pagine di memoria meno utilizzate e le sposta dalla RAM allo swap su disco.
  
- Usa la RAM appena liberata per gestire i processi più usati.
  
- Se quei processi poco usati tornano a servire, li sposta di nuovo in RAM.

Non devi pensarla come "RAM aggiuntiva" (lo swap è assai più lento della RAM) ma come un meccanismo di sicurezza temporaneo.

### **Come viene creato lo swap?**
Dipende da cosa vuoi usare per delimitare lo spazio su disco allocato allo swap.

### **La swap partition**
Una partizione usata come spazio di swap: si trova fuori dal [[Filesystem]] ed è composta da blocchi grezzi su disco.

Come approccio non è molto flessibile: ridimensionarla è complesso perchè devi partizionare il disco.

### **Lo swap file**
Un file formattato come area di swap. È davvero un file, però a differenza di altri file, ci sta di mezzoun trucco software, il [[Kernel]] fa questo:

1. Ottiene la mappatura dei blocchi fisici occupati dal file sul disco.
2. Bypassa il filesystem.
3. Utilizza direttamente quei blocchi grezzi per scrivere\leggere pagine di memoria della RAM.

In questo caso l'area di swap vive dentro al filesystem, ed è un approccio più flessibile della swap partition perchè se vuoi ridimensionare l'area di swap non devi partizionare nulla, puoi scalare facilmente.

### **Lo swap esiste in Windows?**
Sì, ma lì si chiama [[Page File]].

---
