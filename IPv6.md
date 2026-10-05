---
date: 2024-12-26
tags:
  - informatica
  - pubblico

---
# IPv6
***
Un sistema di indirizzamento logico che migliora e punta a sostituire la precedente generazione di indirizzi IPv4 ([[Indirizzo IP (Internet Protocol)]]).

Al momento utilizziamo ancora gli indirizzi IPv4, ma c'è un problema: sono pochi. Quando internet è stato creato ([[Come è nato internet]]) nessuno pensava che avremmo raggiunto un così alto numero di dispositivi che comunicano tra loro, per sopperire alla mancanza di indirizzi IP disponibili abbiam dovuto tirare su tecnologie come il [[NAT (Network Address Translation)]].

Il limite di identificativi unici disponibili nel sistema IPv4 è di 4 bilioni e qualcosa, ma il nuovo sistema IPv6 porta questo tetto in alto: 340,282,366,920,938,463,463,374,607,431,768,211,456 identificativi unici disponibili. È un numero stupidamente alto, sono 340 undicilioni. Vuoi gasarti? [leggiti questo, va.](https://www.reddit.com/r/theydidthemath/comments/2qxgxw/self_just_how_big_is_ipv6/)

Adesso guarda un indirizzo IPv6:
#### `fe80:0000:0000:1234:0000:0000:0000:1234`

###### **Ma è lunghissimo!**
That's what she said, comunque esistono delle tecniche per renderlo più corto:

- Tutti gli zeri iniziali in eccesso possono essere omessi:
	### `fe80:0:0:1234:0:0:0:1234`

- I blocchi consecutivi di soli zeri possono essere sostituiti da due doppi punti, ma solo una volta per evitare ambiguità:
	### `fe80:0:0:1234::1234`



***

