---
date: 2026-06-27
tags:
  - informatica
  - pubblico

---
# DISM (Deployment Image Servicing and Management)
---
Strumento usato per modificare immagini .wim prima di installare Windows, ma oggi viene utilizzato anche per riparare la propria installazione Windows.

Nello specifico, quello che DISM fa è:

- attingere a file sani da Windows Update, o da sorgente locale come ISO
- riparare lo store dei componenti (WinSxS), la cartella dal quale [[SFC (System File Checker)]] prende i propri file.

Generalmente ti conviene lanciare prima DISM e poi SFC, per assicurarti che lo store dei componenti non fosse corrotto in primo luogo.

---