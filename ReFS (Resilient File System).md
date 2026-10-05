---
date: 2026-03-21
tags:
  - informatica
  - pubblico

---
# ReFS (Resilient File System)
---
Un [[Filesystem]] di "nuova generazione" introdotto da Microsoft nel 2012. Prende il nome dalla sua "resilienza" alla corruzione di dati. 

### Quali sono le caratteristiche principali?
È un'architettura scritta per gestire scenari moderni di archiviazione e superare i limiti di [[NTFS (New Technology File System)]].

### Auto-riparazione dei dati
Su un sistema NTFS useresti il comando [[chkdsk]] al bisogno, per riparare dati corrotti. In ReFS questo processo è automatico: 

- Il file system scrive un [[Checksum]] per ciascun file, se qualcosa si corrompe (un [[Bit Rot]] o altro per esempio) allora la firma cambia e il file system lo rileva.
  
- Se hai una copia mirror (vedi [[RAID (Redundant Array of Independent Disks)]]) di quel disco ripara il file automaticamente partendo dalla copia sana, se non la hai allora lo isola per evitare la corruzione si diffonda ad altri file.

### Scalabilità
Supporta file e volumi enormi, fino a 35 petabyte, superando di gran lunga i 256 TB di NTFS.

### CoW (Copy-on-Write)
Un meccanismo per il quale i dati a disco non vengono mai modificati direttamente: quando devono cambiare, il sistema scrive una copia modificata in un'altra posizione, e aggiorna i riferimenti che il file usa per puntare ai blocchi "grezzi" su disco (i dati stanno sui blocchi, il file è solo la mappa che punta ai blocchi).

I dati originali non vengono sovrascritti, saranno rimossi solo quando non servono più (ricorda, non è detto vengano eliminati immediatamente per il modo in cui funzionano i dischi).

In questo modo, eviti di perder dati in caso di corruzione, blackout, o errori vari.

### Gestione dei dischi virtuali
È molto più efficiente rispetto a NTFS nel lavorare assieme a hypervisor di vario tipo.

**Può creare dischi virtuali (VDHX) velocemente:**
- NTFS prende la porzione di disco che serve e ne inizializza (scrivendo zeri) tutti i blocchi da subito
- ReFS invece prenota la porzione di spazio e scrive i blocchi solo quando vengono utilizzati effettivamente.
- La creazione del disco virtuale risulta quasi istantanea, ci guadagni in tempo e operazioni di scrittura.

**Può consolidare snapshot velocemente:**
- In Hyper-V si chiamerebbero "checkpoint" ma è solo Microsoft che fa la Microsoft.
- Le macchine virtuali utilizzano un disco virtuale VDHX.
- Quando crei uno snapshot l'hypervisor ti genera un disco virtuale aggiuntivo che contiene il delta delle modifiche (AVDHX), uno per ogni snapshot che fai (es. hai 10 snapshot, ci son 10 dischi AVDHX).
- Nel caso in cui volessi unire quel delta modifiche al disco base, dovresti consolidare/eliminare lo snapshot (il termine cambia a seconda dell'hypervisor, ma la sostanza quella è).
- NTFS ci metterebbe molto, perchè copia il delta modifiche dai blocchi del disco AVDHX a quello base VDHX.
- ReFS ci mette poco perchè invece che copiare il contenuto del disco AVDHX, aggiorna la mappa del VDHX per farla puntare ai blocchi referenziati dall'AVDHX; se esistono già su disco, perchè ricopiarli e far altro lavoro?

### Perchè non usiamo sempre ReFS allora?
Perchè non è ancora così compatibile e completo come NTFS, ha un paio di limiti:

- **Non puoi farci boot di Windows sopra:** quindi dovresti avere OS in NTFS e dati su partizione ReFS.
  
- **L'auto-riparazione richiede dischi:** se vuoi gli errori si auto-correggano ti serve un disco mirror, altrimenti può solo rilevarli e finirla lì.
  
- **Manca compressione file, crittografia a livello file (EFS), hard link avanzati e alcune funzionalità ACL:** in questo NTFS è più maturo.
  
- **Dà il meglio in scenari enterprise o virtualizzati:** su un PC qualsiasi i vantaggi concreti son meno.

| Caratteristica                         | NTFS                                  | ReFS                              |
| -------------------------------------- | ------------------------------------- | --------------------------------- |
| **Anno di rilascio**                   | 1993                                  | 2012                              |
| **Uso principale**                     | General purpose (OS, PC, file server) | Storage avanzato, Hyper-V, backup |
| **Boot Windows**                       | Sì                                    | No (nella pratica)                |
| **Compatibilità**                      | Alta                                  | Media                             |
| **Copy-on-Write (CoW)**                | No                                    | Sì                                |
| **Auto-riparazione**                   | Limitata (chkdsk manuale)             | Automatica (con ridondanza)       |
| **Performance su VM**                  | Normale                               | Alta                              |
| **Snapshot efficienti**                | No                                    | Sì                                |
| **Compressione file**                  | Sì                                    | No                                |
| **Crittografia file (EFS)**            | Sì                                    | No                                |
| **Permessi (ACL)**                     | Completi                              | Meno completi                     |
| **Hard link**                          | Sì                                    | Limitati                          |
| **Scalabilità su grandi volumi**       | Buona                                 | Alta                              |
| **Frammentazione**                     | Più comune                            | Minore (ma CoW può influire)      |
| **Uso su singolo disco**               | Ottimo                                | Poco frequente, meno vantaggi     |

### Ma non assomiglia a Btrfs?
Sì, assomiglia a [[Btrfs (B-tree file system)]] in filosofia: hanno entrambi strutture ad albero (b-tree), CoW, snapshot efficienti e gestione storage avanzata; non sono però la stessa cosa, Btrfs è un filesystem general purpose mentre ReFS è focalizzato su scenari ben precisi.

---
