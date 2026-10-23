---
date: 2026-10-24-18-20
tags:
  - informatica
  - pubblico
---
# Processo
---
Un'istanza di un programma in esecuzione.

### Come funziona?
Prendiamo un esempio:

- Apri Firefox sul tuo computer.
  
- Il sistema operativo crea uno o più processi per gestire le diverse attività del browser; per esempio potrebbe creare un processo che gestisce interfaccia, finestre e schede, uno che esegue la pagina web, e uno che si occupa di operazioni grafiche su GPU.
  
- Ogni processo ha un proprio spazio di memoria virtuale, tempo di CPU, risorse e permessi.
  
- Ogni processo contiene uno o più thread, sequenze di istruzioni che condividono le risorse del processo, e possono essere eseguite in maniera indipendente l'una dall'altra; per esempio, un thread esegue codice JavaScript, un'altro gestisce alcune operazioni di rendering, altri gestiscono operazioni di rete.

Isolare le attività in processi così è sicuro, perchè se una pagina web provoca un errore grave, può essere arrestata in maniera indipendente dalle altre. A differenza dei processi, i thread dello stesso processo non sono isolati tra loro, quindi un errore grave in un thread può compromettere il processo sopra per intero.

---
