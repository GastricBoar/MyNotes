---
date: 2024-10-11
tags:
  - informatica
  - pubblico

---
# Distinguished Name (DN)
---
Un identificatore univoco che indica la posizione di un oggetto all'interno di una struttura Active Directory.

Un esempio di distinguished name potrebbe essere:

```
DC=poledi,DC=dom
```

Questo DN indica il dominio chiamato "poledi.dom", ma allora perchè non scriverlo semplicemente come "poledi.dom"? Perchè questo non riflette la struttura gerarchica di Active Directory.

Prendiamo per esempio il Distinguished Name:

```
CN=Mario Rossi,OU=Utenti,DC=poledi,DC=dom
```

Questo DN riflette la struttura di Active Directory, ed è il modo corretto per indicare un percorso al suo interno.

---
[[Sincronizzazione Deepser - Active Directory]]