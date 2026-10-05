---
date: 2026-03-17
tags:
  - informatica
  - pubblico

---
# Frammentazione
---
Condizione per il quale i file salvati su disco sono distribuiti in più cluster non contigui.

Prendi questo esempio, in una tabella [[FAT (File Allocation Table)]]:

<img src="Utilities/Media/Pasted%20image%2020260317203836.png" alt="Pasted image 20260317203836.png" width="429">

Ci sono tre file salvati, ma adesso vuoi eliminare quello di mezzo chiamato "important document 31.docx"; facendo questo ti restano cinque cluster liberi in mezzo (quelli con FFF7 sono i danneggiati e li scarti).

Dopo averlo eliminato, vuoi rimpiazzarlo con un file che ti occuperà 6 cluster:

<img src="Utilities/Media/Pasted%20image%2020260317204104.png" alt="Pasted image 20260317204104.png" width="423">

Guarda cosa ha fatto il sistema operativo: i cluster scritti non sono contigui, perchè di mezzo ci stavano dei cluster già occupati da altri file. 

Questa è la frammentazione, e:

- sui dischi meccanici aumenta i tempi di accesso ai file, perchè la testina sopra il disco deve muoversi avanti e indietro tra i settori per ricostruire il file
  
- su [[SSD (Solid State Drive)]] è molto meno un problema, non ci sta nessuna testina che si muove; l'accesso ai blocchi è uniforme e quasi istantaneo, può al massimo causare un piccolo overhead perchè ci sono metadati/operazioni logiche da gestire.

### Come si rimedia alla frammentazione?
Su HDD si risolve con la deframmentazione.

Su SSD non c'è bisogno di risolvere frammentazione. Detto questo, gli SSD seguono meccaniche di ottimizzazione interna, tipo [[TRIM (o ottimizzazione)]]; attenzione, non è che il comando TRIM serva a risolvere la frammentazione.

### Deframmentazione su HDD
Su hardisk utilizzi la deframmentazione, un processo che:

- legge la posizione dei file sui blocchi
- cerca degli intervalli di blocchi contigui
- copia i dati
- aggiorna filesystem (per dire "adesso il file A si trova qui e non lì")
- libera i vecchi blocchi

Se prima avevi il file A sui blocchi 50, 731 e 896, adesso lo hai sui blocchi 50, 51 e 52.

---
