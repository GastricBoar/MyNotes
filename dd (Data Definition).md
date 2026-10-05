---
date: 2026-06-27
tags:
  - informatica
  - pubblico

---
# dd (Data Definition)
---
Strumento Linux che copia e converte dati a basso livello, utilizzato principalmente per clonare dischi, creare immagini, scrivere file ISO su supporti esterni.

A differenza di [[cp (copy)]], non è pensato per gestire normali file o cartelle: cp lavora su filesystem, dd lavora direttamente sui blocchi del dispositivo; non interpreta contenuto, copia byte per byte.

Per fare un esempio:

- hai un disco da 1 TB, con sopra 100GB di foto.
- dd non copierebbe solo i 100GB, ma 100GB di foto e 900GB vuoti, blocco per blocco.

Non sa cosa sia una directory o un filesystem, copia blocchi grezzi e questo lo rende adatto alle operazioni di cui ti parlavo su.

---