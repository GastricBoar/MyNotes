---
date: 2026-03-12
tags:
  - informatica
  - pubblico

---
# FAT (File Allocation Table)
---
Una famiglia di [[Filesystem]] che utilizza la File Allocation Table.

### Perchè si usa ancora?
Nasce nel 1977 alla Microsoft, nonostante sia un filesystem molto vecchio, ancora oggi sopravvive per via della sua semplicità e compatibilità in firmware, o sistemi embedded con poche risorse. Anche la partizione EFI di un sistema [[UEFI (Unified Extensible Firmware Interface)]] è formattata in FAT32.

Nel tempo evolve in FAT12, FAT16, FAT 32 ed exFAT. Una tabella di confronto:

| Versione | Anno | Uso                   | Dimensione cluster tipica | Dimensione file massima | Dimensione partizione massima | Encryption o compressione |
| -------- | ---- | --------------------- | ------------------------- | ----------------------- | ----------------------------- | ------------------------- |
| FAT12    | 1977 | floppy disk           | 512 B – 4 KB              | ~32 MB                  | ~32 MB                        | No                        |
| FAT16    | 1984 | vecchi sistemi DOS    | 2 KB – 32 KB              | 2 GB                    | 2–4 GB                        | No                        |
| FAT32    | 1996 | USB, SD card          | 4 KB – 32 KB              | 4 GB                    | fino a 2 TB                   | No                        |
| exFAT    | 2006 | memorie flash moderne | 4 KB – 32 MB              | ~16 EB                  | ~128 PB                       | No                        |

### Cosa è la File Allocation Table?
È una tabella che tiene traccia di quali [cluster]([[Cluster (o settori) nei filesystem]]) del disco sono allocati a file, e come sono collegati tra loro.

Una tabella FAT16 è più o meno fatta così:

<img src="Utilities/Media/Pasted%20image%2020260315212516.png" alt="Pasted image 20260315212516.png" width="344">

Sulla colonna sinistra il numero del cluster, sulla colonna destra un certo valore.

Sono righe di codici [esadecimali](obsidian://open?vault=la%20baracchina&file=Atlas%2FSistema%20numerico%20esadecimale), per ogni riga quattro cifre esadecimali, ogni cifra esadecimale equivale a 4 bit e quindi i 16 bit totali rimandano al nome FAT16.

Un numero a 16 bit rappresenta 2¹⁶ (o 16⁴) valori diversi, quindi 65.536 valori da 0000 a FFFF, in questo modo qui:

```
0008
0009
000A
000B
000C
000D
000E
000F
0010
0011
0012
0013
0014
0015
0016
0017
0018
0019
001A
001B
001C
001D
001E
001F
0020
```

Prima ho detto "sulla colonna destra un certo valore" di proposito, perchè certi tipi di valori hanno significati specifici:

| Valore | Significato                              |
| ------ | ---------------------------------------- |
| 0000   | cluster libero, non usato da nessun file |
| numero | prossimo cluster del file                |
| FFF7   | cluster danneggiato                      |
| FFFF   | fine del file                            |

### Come viene scritto un file nel pratico?
Immagina di voler salvare una lettera per tua madre, guarda come viene fatto in FAT32:

<img src="Utilities/Media/Pasted%20image%2020260317200523.png" alt="Pasted image 20260317200523.png" width="649">

Il sistema operativo cerca il primo cluster libero, quindi parte dal cluster ABB, poi passa in ABC e ABE, ma qui succede qualcosa: vedi il cluster marcato da FFF7? ecco, è un cluster danneggiato, quindi lo salti e passi ad ABE sotto. Il file finisce in ABE perchè viene marcato come FFFF, end of file. Il nome del file viene scritto in [[Directory nei filesystem]], assieme al cluster di partenza.

### Come viene eliminato un file?
Quando elimini un file, il primo byte del nome viene cambiato in E5 (hex), e i suoi cluster marcati come liberi con 0000; sono ancora lì fisicamente, ma in attesa di esser sovrascritti quando ce ne sarà bisogno.

---
[[Formattazione]]
[[Bit (Binary digit)]]
[[Frammentazione]]