---
date: 2024-12-26
tags:
  - informatica
  - pubblico

---
# Risolvere problemi legati al server DHCP
***
Può capitare un server [[DHCP (Dynamic Host Configuration Protocol)]] abbia problemi o cada giù.

Lato dispositivo, possiam provare a riconnetterci al server DHCP in due modi.
###### **Riconnettersi al server DHCP tramite ipconfig** 
Il metodo più lento, ecco come fare:

1. Accedi al CMD.
2. Invia un [[ipconfig]] per verificare che il tuo PC abbia già preso un [[Indirizzo IP (Internet Protocol)]] privato tramite [[APIPA (Automatic Private IP Addressing)]].
3. Dovesse essere così, invia un `ipconfig /release` per rilasciare il tuo indirizzo IP attuale.
4. Invia un `ipconfig /renew` per chiedere un nuovo indirizzo IP al server DHCP.
###### **Riconnettersi al server DHCP tramite lo strumento di risoluzione dei problemi di Windows** 
Fa essenzialmente quello che hai fatto con il primo metodo, tra le altre cose verifica di raggiungere una serie di siti test:

1. Dai un tasto destro del mouse sull'iconcina della rete in basso a destra della barra applicazioni di Windows.
2. Click su "Diagnostica problemi di rete".
3. Aspetta finisca.
***

