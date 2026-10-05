---
date: 2026-04-05
tags:
  - informatica
  - pubblico

---
# Delayed allocation (in file system)
---
Meccanismo che rimanda l'allocazione dei blocchi fino al momento della scrittura su disco, in modo che il [[Filesystem]] possa scegliere aree di blocchi contigui più grandi.

Il filesystem FAT sceglierebbe i blocchi uno a uno, il primo buco libero che trova mentre scrive, tipo "scelgo il blocco 31, poi il 230, poi il 540, poi il 600 etc."

Con la delayed allocation invece:

1. il programma scrive dati
2. il [[Kernel]] non li alloca subito perchè non sa quale sarà la dimensione finale del file, quindi rimanda un attimo
3. li mette temporaneamente in [[Page cache (su RAM)]], il suo buffer temporaneo per operazioni
4. man mano che il file cresce accumula info su quanti dati scrivere, tipo "mi servono 10 mb, mi servono 50 mb, mi servono 200 mb"
5. quando è ora di scrivere può cercare uno spazio contiguo abbastanza grande, invece che scegliere i primo blocchi disponibili

Questo approccio riduce la [[Frammentazione]] e migliora le performance, ma in caso di crash perderesti quei dati scritti in RAM e dovresti ripartire con l'operazione di scrittura.


---
