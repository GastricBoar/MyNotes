---
date: 2026-08-31
tags:
  - informatica
  - pubblico

---
a# PostScript (PS)
---
Linguaggio di descrizione di pagina (PDL) sviluppato da Adobe nel 1982, progettato per descrivere testo, grafica e immagini.

### Come funziona?
Una tipica elaborazione PostScript funziona così:

- Il computer invia alla stampante un file contenente codice e istruzioni matematiche che devscrivono la pagina (es. "Disegna un cerchio di raggio 3 cm", "Scrivi in Arial", cicli for, condizioni).
  
- Il RIP della stampante interpreta queste istruzioni per produrre l'immagine da stampare.
  
- Lo fa in base alle proprie caratteristiche: su una stampante da 300 DPI il cerchio viene calcolato a 300 DPI, su una stampante a 2400 DPI lo stesso identico cerchio viene stampato a 2400 DPI. 

### Le caratteristiche
In virtù di come funziona, un paio di caratteristiche:

- **È indipendente dal modello del dispositivo:** la stessa descrizione PostScript può essere interpretata da stampanti diverse, senza bisogno di creare una descrizione specifica per modello.
  
- **Alta qualità e coerenza grafica:** poichè la pagina viene ricalcolata dal RIP a partire da codice matematico, mantiene la massima nitidezza possibile e rimane fedele su più stampanti; è anche questo il motivo per il quale veniva molto utilizzato in tipografia, editoria e grafica professionale.

- **Richiede più elaborazione e memoria dalla stampante:** a differenza di PCL, è un linguaggio di programmazione completo e affida più lavoro alla stampante, che deve calcolare equazioni da zero e trasformarle in pixel.

PostScript ha gettato le basi per la nascita del formato PDF, che ha soppiantato il formato PostScript (.ps). Attenzione però: lo ha sostituito come formato di file, non totalmente come linguaggio utilizzato dalle stampanti professionali e tipografiche.

Il PDF a confonto prende gli oggetti descrittivi di PostScript (vettori, font, layout etc.) ma rimuove la parte di programmazione. Il lavoro di calcolo matematico viene svolto dal computer mentre crea il file. Qui ti sto dando una grossa semplificazione, quindi se vuoi approfondisci eh.

### In che modo è diverso da PCL?
Una tabella comparativa:

| **Caratteristica**   | **PostScript (PS)**                                  | **PCL (Printer Command Language)**              |
| -------------------- | ---------------------------------------------------- | ----------------------------------------------- |
| **Natura**           | Linguaggio di programmazione completo                | Insieme di comandi stampa diretti alla macchina |
| **Indipendenza**     | Indipendente dal dispositivo                         | Dipendente da dispositivo e sistema operativo   |
| **Carico di lavoro** | Sulla stampante                                      | Sul computer                                    |
| **Punto di forza**   | Alta fedeltà grafica, vettori e coerenza tipografica | Velocità di stampa e basso uso di memoria       |
| **Uso ideale**       | Grafica professionale, editoria, PDF workflow        | Documenti da ufficio, testo, uso domestico      |

---
[[Page Description Language (PDL)]]
[[PCL (Page Command Language)]]