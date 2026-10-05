---
date: 2025-02-09
tags:
  - informatica
  - pubblico

---
# DSL (Digital Subscriber Line)
---
Il successore delle vecchie [[Connessioni Dial-up]], uno dei primi esempi di [[Connessioni broadband (banda larga)]]. Questo tipo di tecnologia ad accesso a [[Internet]] sfrutta la linea telefonica (con doppino in rame) che già arrivava a casa tua, ma utilizza una frequenza diversa rispetto a quella utilizzata per le chiamate vocali.

##### **Com'è che arrivano a casa mia questi segnali?**
1. La linea parte dal tuo [[ISP (Internet Service Provider)]] che utilizza una rete backbone di livello superiore ([[Livelli di rete internet]]).

2. Arriva alla centrale telefonica.

3. Arriva all'armadio di rete più vicino a casa tua.

4. Arriva alla tua presa a muro, qui avrai bisogno di utilizzare uno sdoppiatore telefonico per separare quello che arriva al tuo modem e quello che arriva al telefono di casa.<img src="Utilities/Media/536_DSL-16MF_A1_Image%20L%28Front%29_web.png" alt="536_DSL-16MF_A1_Image L(Front)_web.png" width="275" height="160">

5. A questo punto arriva al tuo [[Modem]] DSL. Attenzione, il termine "modem" viene ancora usato per abitudine, non è un modem come quello utilizzato nelle connessioni dial-up perchè non modula o de-modula nulla; quello che fa è adattare i dati digitali del segnale DSL in uno standard che il tuo PC possa comprendere, quindi è più un "adattatore di terminali" che altro.

##### **ADSL (Asymmetric Digital Subscriber Line)**
Questo tipo di DSL offre velocità di download molto più alte rispetto a quelle di upload, da qui il termine "Asymmetric". È adatta a chi scarica molto e non esegue grossi upload, come gli utenti domestici; il vantaggio per questi utenti è il costo minore e il fatto che non abbia bisogno di infrastrutture aggiuntive.

##### **SDSL (Symmetric Digital Subscriber Line)**
Questo tipo di DSL invece offre velocità di download pari a quelle di upload. È più adatta ad aziende e usi professionali, dove c'è spesso più bisogno di grossi upload, server e cloud computing. Richiede una connessione dedicata, ed è più costosa.

##### **VDSL (Very-high-bit-rate Digital Subscriber Line) o FTTC (Fiber To The Cabinet)**
Un tipo di DSL che raggiunge velocità molto più alte rispetto alle restanti due versioni; questo è possibile a causa dell'infrastruttura dietro, che mischia fibra e rame: la fibra arriva all'armadio stradale tramite FTTC (Fiber to the Cabinet), l'ultimo pezzo arriva a casa con il doppino telefonico in rame tipico della DSL.

##### **Il PPPoE su connessioni DSL**
Con il passare degli anni le connessioni Dial-up sono scomparse, queste connessioni utilizzavano una tariffa a consumo "paghi per quanto lo usi".

Con le nuove connessioni DSL, il numero di computer in casa è aumentato, e gli ISP avevano bisogno di trovare un modo per fatturare separatamente ciascun dispositivo interno alla rete. A questo scopo è stato tirato in ballo il protocollo [[PPPoE (Point-to-Point-Protocol over Ethernet)]], che richiedeva l'autenticazione di ciascun dispositivo in rete tramite username e password che venivano forniti dall'ISP. 

Il diffondersi dei router ha però ostacolato di nuovo il gioco di fatturazione degli ISP, perchè più dispositivi potevano essere presentati a Internet come uno individuale.

Da lì si son diffuse le tariffe flat, le connessioni illimitate a tariffa fissa che paghiamo oggi; il PPPoE è diventato inutile su questo tipo di connessioni; ci sono però dei casi in cui l'accesso a Internet viene per errore bloccato dal protocollo PPPoE (ancora configurabile sui modem), in questi casi sarà necessario aprire il pannello di configurazione del modem e inserire le credenziali ricevute dal proprio ISP all'interno della sezione relativa al PPPoE.

---
