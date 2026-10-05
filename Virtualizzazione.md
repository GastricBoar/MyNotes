---
date: 2024-11-25
tags:
  - informatica
  - pubblico

---
# Virtualizzazione
---
La pratica di simulare hardware e software in un ambiente virtuale (quindi altro software).
Lo si fa per motivi di costi e convenienza, pensiamo a due ipotesi di business per capire quale sia la più conveniente:

- Un server Windows con servizio email, un server Linux con servizio webserver e un server Unix con database.
- Un unico server con sopra tre virtual machines diverse che gestiscono email, webserver e database utilizzando i tre sistemi operativi menzionati sopra.

I vantaggi del secondo scenario son molti:
- **Risparmio sul costo di hardware, elettricità e manutenzione.**
  
- **Risparmio in spazio occupato.**
  
- **Maggiore portatilità.**
  
- **Migliore scalabilità:** riusciremo a trasferire facilmente le nostre VM su un nuovo server nel caso in cui volessimo passare a un server più recente e prestazionale.
  
- **Utilizzo completo delle capacità computazionali del nostro server:** al giorno d'oggi, i server sono così performanti che è molto difficile sfruttare la loro potenza di calcolo per intero; virtualizzando più server al suo interno riusciremo a sfruttare tutta la capacità di calcolo disponibile.
  
- **Maggiore sicurezza e disaster recovery:** le macchine virtuali sono solo dei file, è possibile caricarle in contemporanea su altre macchine per garantire una maggior continuità operativa.

Per virtualizzare una macchina è necessario un particolare tipo di software, chiamato [[Hypervisor]]

---
