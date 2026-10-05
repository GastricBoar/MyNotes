---
date: 2026-08-31
tags:
  - informatica
  - pubblico

---
# PCL (Page Command Language)
---
Linguaggio di descrizione di pagina (PDL) sviluppato da HP negli anni '80, progettato per l'uso da ufficio e domestico per ottimizzare velocità ed efficienza di stampa.

### Come funziona?
Una tipica elaborazione PDL funziona così:

1. Il driver sul PC converte il documento in comandi semplici e quasi pronti all'uso per la stampante, adattando il flusso al sistema operativo.

2. Invece di inviare codice matematico alla stampante (per come farebbe PostScript), il driver invia alla stampante una serie di comandi stampa specifici (es. "sposta la testina a destra", "stampa questa striscia di pixel").

3. La stampante riceve le istruzioni ed esegue la stampa.

### Le caratteristiche
In virtù di come funziona, un paio di caratteristiche:

- **Dipendente da dispositivo e da sistema operativo:** è legato al sistema operativo del client e al modello di stampante. Produttori diversi possono interpretare il codice PCL in modo leggermente differente, rischiando piccole variazioni nel risultato finale.

- **Basso consumo di risorse:** richiede poca memoria RAM e poca potenza di calcolo dalla stampante, rendendolo ideale per macchine economiche o di fascia media. Eseguire dei comandi di stampa operativi è più veloce che interpretare del codice matematico.

- **Alta velocità:** più rapido di PostScript nell'elaborare documenti standard di testo, tabelle e report da ufficio.

### In che modo è diverso da PostScript?
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
[[PostScript (PS)]]