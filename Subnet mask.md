---
date: 2024-12-23
tags:
  - informatica
  - pubblico

---
# Subnet mask
***
Un numero utilizzato all'interno di una rete, separa la parte dell'[[Indirizzo IP (Internet Protocol)]] che identifica la rete da quella che identifica i dispositivi.

Assomiglia a:
#### `255.255.0.0`

Tutte le posizioni con dentro un 255 non possono cambiare nell'indirizzo, tutte le posizioni con dentro uno 0 lo possono fare.

Grazie a questo numero, il router può capire se un determinato indirizzo IP appartiene alla rete o meno, facciamo un esempio:

1. Immaginiamo un cellulare che fa parte della rete 10.11.12.0, ha indirizzo IP 192.168.0.12 e una subnet mask di 255.255.255.0.
2. Il cellulare vuole comunicare con un PC che fa parte della rete 10.14.6.0.
3. I due indirizzi IP vengono confrontati con la subnet mask: il primo numero di ciascun indirizzo è uguale, ottimo; il secondo e il terzo no, vuol dire che i due indirizzi non appartengono alla stessa rete.
4. Se i due dispositivi non appartengono alla stessa rete, la palla passa al default gateway (il [[Router]]).
***

