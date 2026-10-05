---
date: 2026-08-07
tags:
  - informatica
  - pubblico

---
# SMNP (Simple Management Network Protocol)
---
Un protocollo utilizzato per monitoraggio, gestione e configurazione centralizzata di apparati di rete (router, switch, firewall, server, stampanti) da un'unica postazione di controllo, detta Network Management System (NMS). Opera a livello 7 (applicativo) del modello OSI.

### Come funziona?
Grazie a tre elementi principali:

- **SNMP Manager (o NMS):** Il server centralizzato di monitoraggio (es. PRTG, Zabbix) che invia richieste, riceve notifiche e raccoglie dati.
  
- **SNMP Agent:** un agent attivo sul dispositivo finale, raccoglie le metriche locali e risponde alle interrogazioni del Manager. Su apparati di rete è integrato direttamente nel firmware.
  
- **MIB (Management Information Base):** un database ad albero presente sul dispositivo monitorato. Ogni parametro monitorabile (es. temperatura, utilizzo CPU, stato delle porte) ha un suo indirizzo numerico univoco chiamato OID (Object Identifier).

### Monitoraggio Agentless
Non è raro assistere a sistemi di monitoraggio che operano in modalità agentless, senza necessità di installare un agent SNMP proprietario. Per esempio:

- **Apparati di rete:** il software di monitoraggio interroga direttamente l'agente SNMP nativo integrato nel dispositivo.
  
- **Server e client:** il software di monitoraggio può usare servizi SNMP già integrati a sistema operativo (es. su Windows o su Linux con `net-snmp`), oppure altri protocolli amministrativi nativi del sistema operativo (es. WMI/WinRM per Windows, o SSH per Linux).

### Versioni
Un paio, nel tempo SNMPv1, SNMPv2, SNMPv3.

| Versione | Livello di Sicurezza | Caratteristiche Principali |
| :--- | :--- | :--- |
| **SNMPv1** | Basso | Autenticazione basata su password in chiaro (*Community String*). Supporta solo contatori a 32-bit. |
| **SNMPv2c** | Basso | Autenticazione con *Community String* in chiaro. Introduce i contatori a 64-bit e il comando `GETBULK`. |
| **SNMPv3** | Alto | Standard attuale consigliato. Introduce autenticazione forte (SHA/MD5) e crittografia del traffico (AES/DES). |


---
[[Firmware]]
