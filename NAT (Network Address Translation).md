---
date: 2024-12-11
tags:
  - informatica
  - pubblico

---
# NAT (Network Address Translation)
---









Il NAT blocca anche le connessioni in ingresso verso dispositivi nella rete locale. Questo significa che un computer esterno non può iniziare una connessione diretta al tuo PC dietro un router senza configurazioni aggiuntive (come il port forwarding).

1. **NAT Traversal**:
    
    - È una tecnica che consente di superare questa limitazione. I dispositivi dietro NAT possono comunicare tra loro attraverso un server intermedio che funge da "ponte".
    - In pratica:
        - I dispositivi dietro NAT inviano una richiesta di connessione al server intermedio (che ha un IP pubblico).
        - Il server registra queste richieste e aiuta i dispositivi a stabilire una connessione diretta (se possibile) o agisce da relay (canale intermedio).

---
