---
date: 2025-01-15
tags:
  - informatica
  - pubblico

---
# Loopback address (localhost)
---
Un particolare tipo di [[Indirizzo IP (Internet Protocol)]] utilizzato dal dispositivo per comunicare con sè stesso.

Può essere utile in tantissimi contesti, ma non dilly-dallare perchè sono così tanti che non ha senso conoscerli tutti se non per una specifica applicazione. Vuoi davvero sapere [quanto è profonda la tana del bianconiglio]([Pillola rossa o blu? - Matrix (1999)](https://www.youtube.com/watch?v=ECamB0bcQsY))?

In questa nota lo analizziamo solo perchè ci è utile a [[Fare troubleshooting su reti cablate]].
###### **A cosa assomiglia?** 
Comunemente, è più utilizzato nella forma dell'indirizzo:
##### `127.0.0.1`

Vederlo utilizzato più frequentemente in questa forma non dovrebbe distrarti dal fatto che si tratti di un indirizzo classe A ([[Indirizzo IP (Internet Protocol)]]) come tutti gli altri. Al tempo la scelta venne fatta da chi ha progettato internet, è stata criticata perchè in questo modo son stati esclusi 16 milioni di indirizzi dal pool degli indirizzi disponibili.

In ogni caso, tutto il range 127.x.x.x è riservato agli indirizzi loopback: pingare un `127.0.0.1`, un `127.127.127.127` o un `127.33.33.33` è la stessa identica cosa perchè son tutti indirizzi di loopback.

###### **A cosa è utile?** 
Aspetta qualcuno ti risponda su Reddit, altrimenti inventati tu qualcosa.






---
