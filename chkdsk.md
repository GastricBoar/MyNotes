---
date: 2024-11-06
tags:
  - informatica
  - pubblico

---
# chkdsk
***
Il comando chkdsk è uno degli strumenti di diagnostica in Windows, ti permette di analizzare e riparare errori di [[Filesystem]] unità di memoria.

Si esegue da riga di comando con una sintassi del genere:

```
chkdsk [unità:] [opzioni]
```

Le opzioni più usate sono:

- **/f**: corregge errori sul disco.
- **/r**: individua i settori danneggiati e cerca di recuperare le informazioni leggibili.
- **/x**: forza lo smontaggio del volume prima di controllarlo, se necessario.

Quello che nel pratico fa è scansionare la struttura del filesystem per verificarne la coerenza; per fare un esempio, a seguito di un blackout potrebbero succedere cose tipo:

- catene di cluster spezzate (ABB > ABC > ??? > FFFF)
- file che puntano allo stesso cluster
- cluster orfani, marcati come occupati ma non collegati a nessun file
- cluster danneggiati

A ognuno di questi problemi corrisponde un'azione chkdsk.
***
[[HDD (Hardisk)]]

[[SSD (Solid State Drive)]]

[[FAT (File Allocation Table)]]

