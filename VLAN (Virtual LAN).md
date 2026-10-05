---
date: 2025-01-14
tags:
  - informatica
  - pubblico

---
# VLAN (Virtual LAN)
---
La virtualizzazione di una rete locale ([[LAN (Local Area Network)]], una o più reti logiche virtualizzate a partire da una rete fisica.

Ci sono diversi vantaggi nel segmentare una rete in più VLAN:

- **Sicurezza:** nonostante le reti partano da uno stesso switch, sono tra loro isolate e non comunicanti (a meno che non vengano configurate per farlo). Potrei creare una rete per l'ufficio contabilità e includere un server al quale solo loro devono avere accesso, oppure potrei creare una rete solo per gli ospiti, oppure potrei isolare i sistemi critici dalla rete principale.

- **Personalizzazione:** dispositivi con scopi diversi possono essere organizzati in reti logiche diverse e separate. Potrei creare una rete per i computer, una rete per le stampanti, una rete per i telefoni, una rete per le telecamere e così via.

- **Efficienza:** avere dispositivi di diverso tipo su un unica LAN è poco efficiente; il traffico di rete può esser ridotto se il numero di comunicazioni viene limitato alla piccola cerchia di dispositivi a cui potrebbe effettivamente servire.

###### **Ma come si fa a creare una?**
Devi fare questo:

1. Accedi tramite indirizzo IP al tuo [[Switch]] (trovi le istruzioni all'interno del link).
2. Trovati la sezione che parli di VLAN.
3. Seleziona le porte da usare per la tua VLAN e applica.

---
[VLANs for Beginners]([VLANs for Beginners](https://www.youtube.com/watch?v=12bQIfqBBbQ))