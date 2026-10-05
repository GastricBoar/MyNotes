---
date: 2024-10-22
tags:
  - informatica
  - pubblico

---
# SAS (Serial Attached SCSI)
***
Un'evoluzione della vecchia interfaccia [[SCSI (Small Computer System Interface)]], il grosso cambiamento è stato il passaggio da una connessione parallela (è il fascione di cavetti che si usa sui masterizzatori, ma questo dovresti verificarlo e approfondire in futuro) a una seriale (cavetto singolo e più veloce).

Questo tipo di interfaccia ha delle differenze con le interfacce [[SATA (Serial ATA)]]:

- Raggiunge velocità di 12 GB/s, il doppio rispetto alle interfacce SATA.
- Supporta più dispositivi su singolo bus, fino a 128.
- È altamente affidabile e durevole rispetto all'interfaccia SATA; ha una grande tolleranza agli errori.
- È più costoso.

Ecco una foto di un cavo SAS (nella foto vediamo come un singolo BUS possa ospitare 4 dispositivi):

![Pasted image 20241022213325.png](Utilities/Media/Pasted%20image%2020241022213325.png)

Perchè non preferirlo sempre alle interfacce SATA allora?

Perchè non ne vedremmo molti benefici in ambito consumer, le interfacce SAS vengono usate molto in ambito aziendale e server; quest'interfaccia è più conveniente di SATA nel caso di archiviazione di dati su larga scala dove molte persone hanno bisogno di accedere a quei dati contemporaneamente, e hanno bisogno quell'archiviazione sia affidabile e duratura per un uso 24/7.

***
[[iSCSI (Internet SCSI)]]