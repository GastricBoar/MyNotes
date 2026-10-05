---
date: 2024-12-02
tags:
  - informatica
  - pubblico

---
# Router
***
Un dispositivo di rete utilizzato per connettere più LAN (Local Area Network) in una WAN (Wide Area Network).

![Pasted image 20261005231559.png](Utilities/Media/Pasted%20image%2020261005231559.png)

### Come funziona?
Mettiamo tu abbia comprato uno Switch per creare la tua piccola LAN; ti stai divertendo, sì?
Ecco, adesso stai pensando a quanto potresti divertirti collegando la tua LAN di Bologna con la LAN di un amico che sta a Rotterdam.

Ma come fare allora? fino a quando i dispositivi si parlano tra loro all'interno della stessa stanza o edificio, uno switch basta e avanza, perchè in LAN i dispositivi comunicano tramite i MAC address delle schede di rete. Qui hai invece bisogno di oltrepassare i confini della tua rete locale, ed entra in gioco il router.

Funziona così:

- Connetti il tuo PC allo switch, e lo switch al router; stessa cosa dovrà fare il tuo amico lato suo.
  
- Nell'inviare dati a un dispositivo al di fuori della tua LAN, il tuo PC capisce che l'IP di destinazione non appartiene alla propria rete.
  
- Invia il pacchetto a quello che chiamiamo "Default Gateway", ovvero l'interfaccia lato LAN del tuo router.
  
- Il router riceve il pacchetto e consulta la propria routing table, una tabella che gli permette di capire quale rotta utilizzare per raggiungere la rete di destinazione.
  
- Il pacchetto attraversa una serie di router, ognuno dei quali consulta la propria routing table per decidere verso quale router inoltrarlo.
  
- Il pacchetto arriva finalmente al router del tuo amico, che dentro la sua LAN lo inoltra al dispositivo di destinazione.

Il router è l'[usciere](https://www.youtube.com/watch?v=q0c4Zmsd6fo) della tua LAN, viene detto default gateway.

### I router più utilizzati
A seconda del contesto in cui vengono usati:

- **In ambito enterprise:** Cisco ISR, Cisco Catalyst 8000, Juniper MX Series, Arista 7000 Series.
  
- **In ambito data center:** Cisco Nexus, Juniper MX Series, Arista 7000 Series.

- **In ambito PMI e prosumer:** MikroTik CCR, Ubiquiti UniFi Gateway, Fortinet FortiGate, Cisco Meraki MX.

- **In ambito domestico o Plug & Play:** TP-Link Archer, ASUS RT Series, Netgear Nighthawk, MikroTik hAP.

Qui c'è una differenza rispetto agli switch: FortiGate, Meraki MX e UniFi Gateway sono spesso dispositivi multifunzione, quindi oltre al routing possono offrire firewall, VPN, NAT, DHCP e altre funzionalità.

***
[[LAN (Local Area Network)]]
[[Switch]]
[[WAN (Wide Area Network)]]
[[MAC address]]
[[Internet]]
[[Indirizzo IP (Internet Protocol)]]
