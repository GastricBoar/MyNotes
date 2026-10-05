---
date: 2026-08-31
tags:
  - informatica
  - pubblico

---
# Page Description Language (PDL)
---
Linguaggio di programmazione utilizzato per descrivere l'aspetto visivo di una pagina stampata; agisce da ponte tra client (che genera il documento) e la stampante (che deve riprodurlo su carta).

### Il contesto
Stampare una pagina segue un percorso preciso, ed è necessario far comunicare due dispositivi ben diversi:

- **Il tuo computer:** parla la lingua delle applicazioni, quindi font, coordinate matematiche, immagini.
  
- **La stampante:** parla la dura lingua dei punti di inchiostro da depositare sul foglio.

Adesso immagina di dover stampare una pagina PDF con del testo e un quadrato blu: il tuo computer dovrebbe trasformare quel foglio in un'imponente mappa contenente migliaia di punti di inchiostro. Un'operazione del genere produrrebbe un file più pesante (es. 30-50 Mb) da trasferire via cavo alla stampante, con buona fatica di rete e applicazione su computer.

È qui che diventa utile usare un linguaggio di programmazione, capace di descrivere la pagina tramite istruzioni e vettori invece che pixel.

### Come funziona?
Un PDL è in grado di tradurre il documento in un piccolo file di testo:

- Ne elabora il contenuto tramite formule matematiche, es. "disegna un quadrato blu alle coordinate X,Y" oppure "scrivi il testo in font Arial".
  
- Questo file PDL è piccolo nell'ordine di pochi Kilobyte, e il trasferimento alla stampante dura pochi millisecondi.

- La stampante a questo punto converte il codice PDL in punti di inchiostro usando il RIP (Raster Image Processor), un chip specificatamente ottimizzato per trasformare vettori in matrice di pixel; è comunque laborioso, ma se ne occupa la stampante e ti evita di affollare la rete mantenendo allo stesso tempo il tuo computer disponibile subito.

Volendo entrare nello specifico:

- **Il testo e le forme geometriche vengono vettorializzati:** la stampante riceve una formula matematica di cosa c'è disegnato, il che può essere adattata a qualsiasi dimensione senza mai sgranare.
  
- **Le immagini vengono compresse e trasmesse mantenendo la loro struttura raster:** è una griglia di pixel che segue un certo colore e una certa posizione; essendo questa una quantità fissa di punti, l'immagine può apparire sgranata se non stampata a corretta risoluzione.
  
### Diversi tipi di PDL
Tra i più diffusi:

- **PostScript (PS):** sviluppato da Adobe, è lo standard storico orientato agli oggetti per il mondo della tipografia e dell'editoria professionale.

- **PCL (Printer Command Language):** Sviluppato da HP, è lo standard de facto estremamente diffuso nelle stampanti da ufficio e domestiche.

- **PDF:** Nato come evoluzione "statica" di PostScript. Mantiene la descrizione vettoriale delle pagine ma elimina la componente di programmazione complessa, diventando lo standard universale sia per la visualizzazione a schermo che per la stampa.

---
[[PostScript (PS)]]
[[PCL (Page Command Language)]]
