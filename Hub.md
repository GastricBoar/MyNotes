---
date: 2024-11-28
tags:
  - informatica
  - pubblico

---
# Hub
***
Un hub è un dispositivo di rete utilizzato per collegare più dispositivi all'interno di una [[LAN (Local Area Network)]].

Un hub replica i dati ricevuti e distribuirli a tutti gli host connessi senza riuscire a fare distinzioni. Facciamo un esempio:

- Nella mia LAN ci sono Fabio, Paolo, Anna e Luca. Tutti i dispositivi son connessi a un hub.
- Voglio mandare un "Ciao Fabio!" a Fabio.
- L'hub riceverà i dati dal mio dispositivo, e li replicherà inviandoli a tutti i dispositivi connessi.
- Fabio riceverà il mio messaggio, ma anche Paolo, Anna e Luca.
  
Un hub diventa difficile nel momento in cui più host cercano di comunicare contemporaneamente:

- Nella LAN di cui parlavamo prima, Anna e Luca vogliono mandarsi un messaggio; anche Fabio e Paolo vogliono mandarsi un messaggio (sono omosessuali).
- Il nostro hub ha un throughput massimo di 10 Mb/s.
- Il throughput totale è diviso tra le due coppie, avremo solo 5 Mb/s assegnati a ogni comunicazione. (non ne sono sicuro, questa era una cosa che hai sentito dal corso di Mike Meyers ma di cui non sei sicuro).
***
[[Switch]]
