---
date: 2026-03-09
tags:
  - informatica
  - pubblico

---
# GPT (GUID Partition Table)
---
Uno schema di partizionamento moderno, contiene la tabella delle partizioni e si utilizza nei sistemi [[UEFI (Unified Extensible Firmware Interface)]]. 

Il tuo PC ha bisogno di sapere dove siano le partizioni, e quale di queste contenga cosa; il GPT fa esattamente questo: descrive la struttura del disco.

### Come identifica le partizioni?
A ciascuna partizione viene assegnato un [[GUID (Globally Unique Identifier)]], lo hai tu e nessun altro; è importante sia unico, perchè ti permette di indicare una partizione ben precisa a prescindere da altri fattori hardware e software.

### Come organizza il disco?
Tramite un paio di strutture importanti.

### Il protective MBR
Immagina lo scenario: usi un disco GPT sul tuo sistema, ma poi rimuovi quel disco e lo usi su un vecchio PC che il GPT non lo supporta; quel sistema proverà a leggere la tabella delle partizioni, e non riconoscendola penserà di inizializzare il disco per ripartizionare tutto da zero con una tabella MBR.

Per evitare i vecchi sistemi sovrascrivano le tabelle GPT, entra in gioco il protective MBR: una tabella MBR che tramite una sola voce dice al sistema "esiste una sola partizione e occupa tutto il disco"; basta questo a far capire che il disco è già partizionato e che non è necessario intraprendere altre azioni.

La stessa partizione di cui si parlava prima utilizza un codice convenzionale che, quando interpretato da un sistema GPT, dice "questo disco usa GPT" facendolo proseguire verso la tabella delle partizioni vera e propria.

### Il GPT header primario
Eccolo, l'erore; contiene informazioni sulla struttura della tabella delle partizioni.

### Il GPT header secondario
Una copia backup di header primario e tabella partizioni; se la tabella primaria viene danneggiata per qualche motivo, può sostituirla e ricostruirla da capo. I dischi GPT son belli perchè, in un certo senso, sono auto-medicanti.

### Come avviene l'avvio del sistema operativo?  
Abbiamo visto che il MBR contiene codice di avvio, ma nei sistemi GPT è diverso: il processo di avvio avviene tramite [[UEFI (Unified Extensible Firmware Interface)]]: 

1. il firmware UEFI legge la struttura GPT del disco  
2. cerca una partizione speciale chiamata **EFI System Partition** (ESP) 
3. dentro questa partizione trova i file di boot del sistema operativo (es. `\EFI\Microsoft\Boot\bootmgfw.efi`) 
4. UEFI esegue direttamente questo file, che poi carica il sistema operativo.

### Il confronto con MBR
GPT è un grosso passo in avanti rispetto a [[MBR (Master Boot Record)]], per diversi motivi. Qui una tabella di confronto:

| Caratteristica                | MBR (Master Boot Record)               | GPT (GUID Partition Table)            |
| ----------------------------- | -------------------------------------- | ------------------------------------- |
| Numero massimo di partizioni  | 4 partizioni primarie                  | Illimitate, ma fino 128 su Windows    |
| Partizioni estese             | Necessarie per superare il limite di 4 | Non esistono                          |
| Dimensione massima disco      | Circa 2 terabyte                       | 9.4 zettabyte (9.4 miliardi TB)       |
| Ridondanza tabella partizioni | Nessuna                                | Tabella duplicata con copia di backup |
| Compatibilità                 | Supportato da sistemi molto vecchi     | Richiede sistemi moderni (UEFI)       |
| Codice di avvio               | Contiene codice di bootstrap           | Non contiene codice di boot           |

---