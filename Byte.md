---
date: 2026-10-10-16-39
tags:
  - informatica
  - pubblico
---
# Byte
---
Un'unità di informazione digitale composta da 8 bit. Non è da confondere con il bit, che invece è l'unità *minima* dell'informazione digitale.

### Come funziona?
8 bit formano un byte (B), e proprio per questo può rappresentare 256 combinazioni di valori diverse; dal calcolo 2⁸ escono fuori 256 combinazioni diverse di una stringa da 8 bit, quindi composta solo da 0 e 1.

### Che differenza fa con il bit?
Qui serve elencare un paio di differenze pratiche:

- Durante la trasmissione su cavo, il dispositivo ricevente interpreta variazioni nel segnale elettrico come valori binari, quindi bit, trasmessi uno alla volta e non raggruppati in byte. La velocità di rete si esprime in bit/s per questo.
  
- Dimensioni e spazio di archiviazione si esprimono in byte.

### Multipli decimali e binari
Puoi esprimere multipli delle unità informatiche con il sistema decimale (multipli di 10) oppure con quello binario (multipli di 2):

- **Kilobyte (kB):** utilizza il sistema decimale, rappresenta 1.000 byte, ovvero 10³ byte. Viene utilizzato spesso in contesti commerciali da produttori di dispositivi di archiviazione, perchè avere una misura che segue il sistema decimale è coerente con il sistema internazionale di unità.

- **Kibibyte (KiB):** utilizza il sistema binario, rappresenta 1.024 byte, ovvero 2¹⁰ byte. Poichè i computer lavorano con dati binari, è più utile rappresentare in multipli binari la quantità di dati; per esempio i sistemi operativi lo usano per esprimere la quantità di RAM.

Un SSD da 500 GB contiene 500 miliardi di byte, equivalenti a circa 465,66 GiB, con un kB che è uguale a 0,98 KiB; la capacità è la stessa, ma a seconda del contesto cambia l'unità di misura utilizzata per esprimerla. Qui una tabella:

| Unità      | Simbolo | Byte in fattore decimale | Unità binaria | Simbolo | Byte in fattore binario |
| ---------- | ------- | ------------------------ | ------------- | ------- | ----------------------- |
| Byte       | B       | 1                        | Byte          | B       | 1                       |
| Kilobyte   | kB      | 10³                      | Kibibyte      | KiB     | 2¹⁰                     |
| Megabyte   | MB      | 10⁶                      | Mebibyte      | MiB     | 2²⁰                     |
| Gigabyte   | GB      | 10⁹                      | Gibibyte      | GiB     | 2³⁰                     |
| Terabyte   | TB      | 10¹²                     | Tebibyte      | TiB     | 2⁴⁰                     |
| Petabyte   | PB      | 10¹⁵                     | Pebibyte      | PiB     | 2⁵⁰                     |
| Exabyte    | EB      | 10¹⁸                     | Exbibyte      | EiB     | 2⁶⁰                     |
| Zettabyte  | ZB      | 10²¹                     | Zebibyte      | ZiB     | 2⁷⁰                     |
| Yottabyte  | YB      | 10²⁴                     | Yobibyte      | YiB     | 2⁸⁰                     |
| Ronnabyte  | RB      | 10²⁷                     | Robibyte      | RiB     | 2⁹⁰                     |
| Quettabyte | QB      | 10³⁰                     | Quebibyte     | QiB     | 2¹⁰⁰                    |

### Altre unità
Il nibble, che è uguale a metà byte o 4 bit.

---
[[Bit (Binary digit)]]
[[Nibble]]