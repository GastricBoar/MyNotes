---
date: 2026-04-18
tags:
  - informatica
  - pubblico

---
# ZTI (Zero Touch Installation)
---
Un approccio al provisioning di sistemi (PC, server, apparati di rete etc.) completamente automatizzato, non richiede alcun intervento umano.

Per fare un esempio:
- hai 100 nuovi PC da configurare
- prendono DHCP dallo switch
- scaricano OS da un server [[PXE (Preboot Execution Environment)]] o [[iPXE (improved PXE)]]
- entrano a dominio, prendendone le policy
- PC pronto

Ci sono strumenti pensati per fare ZTI, tra questi ce ne sono anche alcuni in ambiente cloud, come Windows Autopilot.

---
[[LTI (Lite Touch Installation)]]