---
date: 2025-01-14
tags:
  - informatica
  - pubblico

---
# Routing table
---
Una tabella interna a ogni [[Router]], memorizza le destinazioni percorse nel tempo.
###### **La differenza con la MAC address table** 
La routing table non deve essere confusa con la MAC address table di uno switch:

- La MAC address table contiene tutti i [[MAC address]], ed è il passaggio finale nella consegna di un pacchetto. Lo switch consulta questa tabella per capire a quale dispositivo bisogni recapitare il pacchetto.

- La routing table è diversa e in tutta quella catena di montaggio viene prima rispetto alla MAC address table. Il router la consulta per verificare che il dispositivo al quale deve essere consegnato il pacchetto esista all'interno della rete, per esempio potrebbe verificare che il dispositivo 192.168.7.59 esista all'interno della rete 192.168.7.0/64.
---
[[Indirizzo IP (Internet Protocol)]]