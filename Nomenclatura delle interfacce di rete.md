---
date: 2026-10-06-14-59
tags:
  - informatica
  - pubblico
---
# Nomenclatura delle interfacce di rete
---
A guardare la CLI di un dispositivo di rete qualsiasi, ti sarà capitato di leggere cose come `GigabitEthernet0/0/0`, `GigabitEthernet1/1` o `FastEthernet0/3`. Questi nomi identificano in maniera univoca le diverse interfacce di rete presenti sul dispositivo. 

### Come funziona?
La struttura di quei numeri non è che segua una regola universale, il loro significato dipende da tante cose: il modello del dispositivo, il tipo di dispositivo, la sua struttura hardware, il modo in cui il produttore ha scelto di identificare le interfacce.

Per fare degli esempi:

- Guardi uno switch Cisco, e da CLI leggi `GigabitEthernet2/0/7`. In quel caso, se la documentazione te lo conferma, significa che si tratta della porta 7 dello specifico switch 2 in uno stack di switch impilati.
  
- Guardi uno switch Cisco, e da CLI leggi `GigabitEthernet3/1/4`. In quel caso, se la documentazione te lo conferma, significa che si tratta della porta 4 appartenente allo slot 1 dello switch 2 in uno stack di switch impilati. Qui si parla di uno switch con più slot, e gli slot sono alloggiamenti fisici del dispositivo, nei quali possono essere installati moduli di diverso tipo; per esempio potresti avere un modulo con porte Gigabit e un modulo con porte SFP+.

- Guardi un router Cisco, e da CLI leggi `GigabitEthernet2/6/8`. In quel caso, se la documentazione te lo conferma, si tratta della porta 8 del subslot 6 appartenente allo slot 2. Il subslot è un livello di organizzazione hardware presente su alcune piattaforme, es. uno slot può ospitare una scheda che a sua volta è organizzata in più sezioni hardware, e quella nomenclatura aiuta a distinguere con precisione a quale parte dell'hardware appartiene una determinata porta.

- Guardi un firewall Cisco, e da CLI leggi `GigabitEthernet1/2`. In quel caso, se la documentazione della piattaforma te lo conferma, si tratta della porta 2 appartenente allo slot 1.

Questi esempi ti dicono alcune cose:

- Non tutti gli switch usano nomenclature a tre numeri: uno switch Cisco può avere, per esempio, interfacce come `GigabitEthernet0/1`.
  
- Anche quando due switch usano una nomenclatura a tre numeri, quei numeri non hanno necessariamente lo stesso significato: dipende dalla piattaforma e dalla sua organizzazione hardware.
  
- La nomenclatura non dipende necessariamente solo dal produttore: uno switch Aruba, per esempio, può utilizzare una struttura diversa da quella di uno switch Cisco.
  
- Lo stesso tipo di nomenclatura può assumere significati diversi anche tra dispositivi dello stesso produttore: una nomenclatura a tre numeri su uno switch Cisco non è necessariamente interpretabile nello stesso modo su un router o su un firewall Cisco.
  
- Per questo motivo, quando incontri una nomenclatura che non conosci, non devi cercare di interpretarla basandoti soltanto sulla posizione dei numeri: devi leggere la documentazione e verificare come quella specifica piattaforma identifica le proprie interfacce. Non esiste una convenzione universale.

---
[[Switch]]
[[Router]]
[[Firewall]]
