---
date: 2025-01-14
tags:
  - informatica
  - pubblico

---
# SOHO router (Small Office Home Office)
---
Un tipo di [[Router]] specificatamente pensato per piccoli uffici o uso domestico.

Rispetto a un router aziendale è più economico, più semplice da configurare e incorpora le funzionalità di altri dispositivi come [[Switch]], access point, modem, firewall e così via.

Viene chiamato "router" per convenzione, ma è un accrocchio di tante cose.
###### **Come accedo al pannello di configurazione del mio router SOHO?**
Questi affari son costruiti per connettersi a internet out-of-the-box, il che può essere anche un rischio. Ci sono delle cose che dovresti sapere come configurare, per accedere al pannello di configurazione di questo router ti serve il suo indirizzo IP.

###### **Configurare username e password per l'accesso al pannello di configurazione**
Tutti i pannelli di configurazione sono simili in funzionalità, ma diversi nell'aspetto. Ci sta una sezione dedicata al cambio username e password.

###### **Impostare l'indirizzo IP del router**
Il router è un server [[DHCP (Dynamic Host Configuration Protocol)]] nei confronti della LAN, ma è anche un client nei confronti della [[WAN (Wide Area Network)]]. 

L'indirizzo IP lato WAN viene assegnato dall'ISP tramite DHCP o tramite indirizzo statico, puoi cambiare la modalità di assegnazione dell'indirizzo IP ma su questo dovresti avere istruzioni direttamente dal tuo ISP; nel caso dell'indirizzo statico, ti dovrà esser dettato.

L'indirizzo IP lato LAN viene assegnato di default, ma può esser cambiato a tuo piacimento. Per esempio, potresti voler assegnare l'indirizzo 10.11.12.1; attenzione però, quando fai questo potrebbe succedere che i dispositivi connessi al tuo router non passino automaticamente al nuovo gateway e rimangano perciò tagliati fuori da internet fino a quando non avrai assegnato tu manualmente il nuovo indirizzo. Raramente succederà con dei dispositivi moderni, ma devi comunque saperlo. 

###### **Definire range, lease e reservations DHCP**
Ci sono delle configurazioni che permettono di definire tutto ciò che ci serve. ([[DHCP (Dynamic Host Configuration Protocol)]]).

###### **Configurare o limitare l'accesso al pannello di controllo del router**
Per impostazione di default, basta esser parte della LAN e conoscere l'indirizzo IP del router per connettersi al suo pannello di controllo. Questo può essere un rischio, e ci sono diversi modi per configurare o limitare questo accesso:

- **Limitare l'accesso a determinati MAC address:** solo chi è connesso in LAN e ha un [[MAC address]] autorizzato potrà connettersi.

- **Abilitare l'accesso remoto:** abilitandolo e specificando un numero di porta, potrai accedere al pannello di controllo tramite il suo indirizzo pubblico lato WAN seguito dal numero di porta. Per esempio: 87.93.54.32:8181. Questa è una cosa poco sicura, e Mike Meyers lo sconsiglia.






###### ****




---
