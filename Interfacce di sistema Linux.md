---
date: 2026-10-24-17-01
tags:
  - informatica
  - linux
  - pubblico
---
# Interfacce di sistema Linux
---
I meccanismi attraverso cui i programmi comunicano con il sistema operativo per utilizzare le sue funzionalità.

### Come funziona?
Un programma, parte dello user space, non può accedere direttamente a risorse protette come memoria o hardware: non può leggere direttamente i dati da un disco, ha bisogno di chiedere permesso al kernel, e lo fa tramite un'interfaccia di sistema.

### Tipi di interfacce di sistema
Non esiste un unico tipo di interfaccia di sistema, i programmi possono utilizzare diversi meccanismi per accedere alle funzionalità del sistema operativo:

- **System call:** permettono ai programmi di richiedere operazioni al kernel (es. leggere file, creare processi, utilizzare la rete).

- **Librerie di sistema:** mettono a disposizione funzioni condivise che i programmi possono utilizzare per operazioni comuni, senza doverne per forza implementare ogni dettaglio. Alcune di queste funzioni possono interagire con il kernel tramite system call.

- **API:** definiscono le regole attraverso cui un programma può utilizzare le funzionalità offerte da librerie e servizi.

- **Interfacce a riga di comando (CLI):** permettono agli utenti di interagire con il sistema attraverso comandi testuali, per esempio tramite una shell Bash.

- **Interfacce grafiche (GUI):** permettono agli utenti di interagire con il sistema attraverso finestre, pulsanti e menu, per esempio KDE.

---
[[Kernel]]
[[User space (o userland)]]
[[API (Application Programming Interface)]]
[[Sistema operativo]]