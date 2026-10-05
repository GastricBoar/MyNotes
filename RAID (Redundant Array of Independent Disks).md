---
date: 2024-10-23
tags:
  - informatica
  - pubblico

---
# RAID (Redundant Array of Independent Disks)
***
Redundant Array of Independent Disks, è una tecnologia che combina più dispositivi di archiviazione ([[HDD (Hardisk)]] o [[SSD (Solid State Drive)]]) per migliorarne prestazioni, affidabilità o entrambe.

Esistono diversi tipi di RAID, detti livelli.

### RAID 0 (striping)
Divide i dati tra due dischi, ogni disco contiene parte di un'informazione aumentando la velocità di lettura dei dati.

Aumenta il rischio di perdita dei dati: se uno dei due dischi si rompe perdi i dati per intero.

<img src="Utilities/Media/Pasted%20image%2020241023210404.png" alt="Pasted image 20241023210404.png" width="457">

### RAID 1 (mirroring)
Replica i dati su due dischi, ogni disco contiene la stessa esatta informazione.

Offre ridondanza perchè se uno dei due dischi si guasta hai comunque backup sull'altro; di contro, sacrifichi la metà della capienza dei dischi.

<img src="Utilities/Media/Pasted%20image%2020241023210708.png" alt="Pasted image 20241023210708.png" width="463">

### RAID 10
Anche detto RAID 1+0, combina la velocità del RAID 0 e la ridondanza del RAID 1. 

Ti servono 4 dischi:

- i dati vengono replicati (mirroring) in RAID 1 sulle due coppie di dischi
- poi divisi (striping) tra le coppie di dischi tramite RAID 0
- i tuoi file sono al sicuro fino a quando non si guasta più di un disco per ogni coppia

Il RAID 10 ti dà alte prestazioni e altà affidabilità, ma di contro riduce lo spazio di archiviazione a disposizione: metà della capacità totale viene utilizzata per il mirroring dei dati. 

<img src="Utilities/Media/Pasted%20image%2020241023212007.png" alt="Pasted image 20241023212007.png" width="464">

### RAID 5
Necessita di almeno tre dischi, divide (striping) su ciascun disco sia i dati che la [[Parity]]; 

Ti permette di ricostruire i tuoi dati a patto che non più di un disco fallisca. In capacità di archiviazione hai un limite: la somma delle parity distribuite è uguale alla capacità di un intero disco in array.

<img src="Utilities/Media/Pasted%20image%2020241024211022.png" alt="Pasted image 20241024211022.png" width="465">

### RAID 6
Funziona in maniera simile al RAID 5, ecco un confronto:
 
- necessita di almeno 4 dischi, e non 3.
- dati e parity vengono distribuiti (striping) tra i dischi, ma la parity viene distribuita due volte.
- i dischi occupati dalla parity sono il doppio rispetto al RAID 5, essendo distribuita due volte.

Velocità di lettura rimane uguale al RAID 5, e i dati rimangono protetti anche nello sciagurato caso in cui ti si rompano due dischi contemporaneamente; di contro, la velocità di scrittura risulta più lenta perchè il disco scrive più parity del RAID 5.

<img src="Utilities/Media/Pasted%20image%2020241024211236.png" alt="Pasted image 20241024211236.png" width="472">

Devi ricordare che il sistema operativo riconosce un'unico volume di memoria anche se utilizzi due, quattro o dieci dischi per il tuo RAID.

### Come faccio RAID?
In diversi modi, a seconda dello scenario in cui ti trovi. Tieni a mente che utilizzare dischi che hanno capacità diverse è uno spreco, perchè ti verranno tagliati alla dimensione del più piccolo tra loro (es. 2 dischi da 40 GB e uno da 50 GB, ne ricavi tre dischi da 40 GB).

### Hardware RAID
Usi un controller fisico dedicato (es. una scheda PCIe o un controller built-in su server) e poi:

- accedi al BIOS, cambi modalità del controller SATA 
- da [[AHCI (Advanced Host Controller Interface)]] a RAID
- riavvia e torni al BIOS
- selezioni dischi e il tipo di RAID da costruire
- fatto, da più dischi fisici hai inizializzato un unico volume logico
- il sistema operativo vede quel volume, perchè il RAID esiste prima ancora del boot

<img src="Utilities/Media/Pasted%20image%2020260406153016.png" alt="Pasted image 20260406153016.png" width="555">


**Un controller per hardware RAID ha una serie di vantaggi:**

- **è indipendente dal sistema:** Windows o Linux che sia vede un disco pronto a prescindere
  
- **ha una sua [[CPU (Central Processing Unit)]]:** quindi il calcolo di operazioni pesanti (tipo della parity) viene gestito dal controller velocemente
  
- **ha tante funzioni:** tipo hot swap (cambi un disco rottoBBU senza spegnere il server) e rebuild automatico (cambi disco, e lui ricostruisce automaticamente il RAID)
  
- **ha una sua cache:** il controller scrive tutto in questa cache RAM molto veloce, e smaltisce la scrittura sul disco con calma dopo; ha senso perchè senza cache attendere il disco scriva 100 operazioni ti tiene ferma la CPU e rallenta il resto, con la cache invece tieni tutto in buffer temporaneo e poi scrivi a ritmo cadenzato nel tempo

- **quella cache ha una [[BBU (Backup Battery Unit)]]:** senza una batteria, perderesti i dati accumulati in cache; una batteria di riserva ti permette di tenere tutto in cache per un certo periodo di tempo (es. 3 giorni?) fino a quando non riuscirai a scrivere di nuovo
  
- **è affidabile in ambienti di produzione**
  
**Ci sono degli svantaggi però:**

- **costa:** parte da un centinaio di euro per arrivare alle migliaia sui modelli enterprise più seri
  
- **introduce un certo vendor lock-in:** ogni produttore ha i propri strumenti, e se si rompe ti serve lo stesso modello (o compatibile) per tornare a leggere i dischi

### Software RAID
Usi un software dedicato, per fare RAID tramite la CPU del tuo computer. Per esempio, [[Storage Spaces (su Windows)]].

Il software RAID è gratuito o meno costoso, ma ne soffri in funzioni e performance sulle CPU meno capaci.


--- 
[[Dischi dinamici in Windows]]

PowerCert, [What is RAID 0, 1, 5, & 10?]([What is RAID 0, 1, 5, & 10?](https://www.youtube.com/watch?v=U-OCdTeZLac))

PowerCert, [RAID 5 vs RAID 6]([RAID 5 vs RAID 6](https://www.youtube.com/watch?v=UuUgfCvt9-Q))