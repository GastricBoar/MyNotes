---
date: 2026-09-08
tags:
  - informatica
  - pubblico

---
# Supply Chain Attack
---
Attacco informatico in cui un attaccante compromette un'organizzazione attraverso un fornitore, un software, un servizio o altro componente della sua supply chain, sfruttando il rapporto di fiducia esistente con l'organizzazione.

### Come funziona?
Per fare un esempio, un'azienda utilizza un software fornito da una società esterna:

- L'attaccante compromette il sistema del fornitore.

- Inserisce codice malevolo all'interno del software.

- Il fornitore distribuisce normalmente l'aggiornamento ai propri clienti.

- L'azienda installa l'aggiornamento, ritenendolo legittimo.

- Il codice malevolo viene quindi eseguito all'interno dell'infrastruttura dell'azienda.

Il punto è che l'attaccante non attacca direttamente la vittima finale, ma ne sfrutta un elemento della catena di fiducia a proprio vantaggio.

### Come si previene?
La difesa principale consiste nel controllare e ridurre i rischi derivanti dalle dipendenze esterne, senza dare per scontato che un componente proveniente da una fonte fidata sia automaticamente sicuro:

- **Verifica i fornitori:** valuta le loro pratiche e i loro requisiti di sicurezza.

- **Verifica gli aggiornamenti:** utilizza firme digitali e meccanismi di verifica dell'integrità del software.

- **Monitora le dipendenze:** mantieni sotto controllo librerie, componenti e software di terze parti utilizzati dall'organizzazione.

- **Limita i privilegi:** come sempre, assegna ai componenti e ai fornitori solo gli accessi realmente necessari.

- **Segmenta la rete:** limita la possibilità che una compromissione si propaghi agli altri sistemi.

---
[[BEC (Business Email Compromise)]]