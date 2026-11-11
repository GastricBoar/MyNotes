---
date: 2026-11-12-18-44
tags:
  - informatica
  - pubblico
---
# Modalità wireless Mikrotik
---
Modalità che definiscono come un'interfaccia wireless si comporta nella comunicazione con gli altri dispositivi della rete.

### Come funziona?
Ce ne sono un paio, e ognuna di queste con un ruolo diverso:

- `ap` (Access Point): crea una rete Wi-Fi alla quale possono collegarsi altri dispositivi.

- `station`: si collega a una rete Wi-Fi esistente come client.

- `station-wds`: utilizza WDS per realizzare un collegamento wireless in modalità bridge.

- `station-pseudobridge`: simula un bridge traducendo gli indirizzi MAC dei dispositivi collegati a valle.

- `station-pseudobridge-clone`: variante della modalità pseudobridge che utilizza un indirizzo MAC clonato.

- `station-bridge`: permette di realizzare un bridge wireless trasparente con un Access Point MikroTik compatibile.

---