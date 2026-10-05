---
date: 2025-02-03
tags:
  - informatica
  - pubblico

---
# Livelli di rete internet
---
Una suddivisione gerarchica dell'infrastruttura che compone Internet, vengono detti tier o reti di X livello.
##### **Il contesto**
Nell'articolo su [[Internet]] hai visto come negli anni '70 e '80 le reti sperimentali e Internet stesso venivano gestite da enti governativi o università. Ecco, il problema di questa cosa è che il governo non voleva occuparsi di progettare e gestire una rete mondiale direttamente.

Internet è stato quindi privatizzato, le telecomunicazioni sono diventate un settore aperto al mercato; sai chi ne ha approfittato? le grandi aziende di telecomunicazioni, che hanno ereditato parte delle infrastrutture già esistenti, e si sono impegnate nel costruire cavi sottomarini, infrastrutture e dorsali che potessero connettere il mondo intero.

##### **I provider di primo livello**
Quelle aziende di cui parlavo sono chiamate **"Provider di reti tier 1"**, sono molto grosse/potenti e al giorno d'oggi sono:

![Pasted image 20250204205228.png](Utilities/Media/Pasted%20image%2020250204205228.png)

##### **Gli accordi di peering**
Queste compagnie sono tra loro in competizione, ovviamente; probabilmente vorrebbero vedersi fallire a vicenda, ma c'è una cosa che nessuno di loro può fare individualmente: coprire il mondo intero.

Certo, ognuna di queste compagnie ha grandi reti e infrastrutture, ma ad un certo punto il territorio di un provider diventa parte di un altro; a quel punto, il pensiero comune è stato "costruire un'infrastruttura dove già ne esiste una costerebbe moltissimo, che ne dici di condividere le nostre reti a vicenda? se accetterai, nessuno dei due pagherà nulla all'altro in cambio".

I provider di tier 1 in giro per il mondo hanno stretto un accordo detto "di peering" ; "peer" in italiano significa "pari", e nel gergo informatico vuol dire "scambio di traffico". Condividere queste infrastrutture è molto complesso, ma un mix di edifici viene adibito a questi scopi: data center, [[NOC (Network Operation Center)]], [[IXP (Internet Exchange Points)]] e stazioni di atterraggio cavi sottomarine.

Questi posti sono spaventosi e devono essere super sicuri: edifici anonimi in riva al mare/non segnalati sulle mappe, tunnel sotterranei, centrali fredde, rumore di ventole e trasformatori; vengono protette in qualsiasi modo da guardie armate, filo spinato, telecamere, controlli biometrici, droni subacquei e tutto quello che serve.

##### **Gli altri provider (tier 2, tier 3, tier 4)**

![Pasted image 20250204212442.png](Utilities/Media/Pasted%20image%2020250204212442.png)

---
[Un bel video di Linus](https://www.youtube.com/watch?v=n71TUnTNdw8)