---
date: 2026-08-27
tags:
  - informatica
  - pubblico

---
# ACPI (Advanced Configuration and Power Interface)
---
Standard che permette al sistema operativo di configurare e gestire l'hardware e il consumo energetico del computer attraverso un'interfaccia comune.

Permette al sistema operativo di controllare e gestire diversi aspetti dell'hardware, soprattutto quelli legati al consumo energetico. Per fare un esempio:

- Il sistema operativo rileva che il computer non viene utilizzato.
- Tramite ACPI può chiedere all'hardware di entrare in uno stato a basso consumo.
- Quando l'utente torna a utilizzare il computer, il sistema può ripristinare lo stato operativo.

### Come funziona?
Il sistema operativo non conosce necessariamente i dettagli specifici dell'hardware su cui è installato: sarebbe impraticabile che il sistema operativo prevedesse una gestione specifica per dieci mila modelli di schede madri diverse e per ogni configurazione hardware possibile.

Il firmware (come UEFI o BIOS) invece conosce l'hardware specifico della macchina, perché viene fornito dal produttore della scheda madre ed è progettato per inizializzare e gestire quella specifica piattaforma: sa che ci stanno due banchi di RAM, sa che ci sta una CPU di un certo tipo, o che è presente un pulsante di accensione. Quale candidato migliore per candidato migliore per comunicare queste informazioni al sistema operativo?

Il problema è che ogni produttore potrebbe decidere un modo diverso per farlo: un firmware ASUS potrebbe comunicare in un modo, uno Lenovo in un altro, il sistema operativo dovrebbe conoscere le modalità specifiche di ogni produttore.

Qui ACPI risolve il problema definendo uno standard comune: indipendentemente dal produttore o dal modello della macchina, il firmware può fornire in maniera ordinata informazioni sull'hardware e sulle sue funzionalità al sistema operativo.

ACPI non è un protocollo, ma uno standard; All'avvio del computer succede questo:

- Il firmware rileva che il computer dispone di una batteria, di un pulsante di accensione e di determinate modalità di sospensione.
  
- Inserisce queste informazioni nelle tabelle ACPI, descrivono l'hardware e il modo in cui il sistema operativo ci può interagire.
  
- Il sistema operativo legge le tabelle e può utilizzare queste informazioni per gestire ciò che riguarda l'hardware, per esempio l'alimentazione, la chiusura del coperchio, la pressione del pulsante di accensione, la sospensione del sistema etc.

### Gli stati di alimentazione
ACPI definisce degli stati di alimentazione, indicano quanto è attivo il computer e quali componenti possono essere spenti o messi a basso consumo:

- **S0:** sistema completamente operativo.
  
- **Da S1 a S3:** diversi livelli di sospensione, con una quantità crescente di componenti spenti o a basso consumo (es. S3 mantiene la RAM alimentata, ma spegne CPU e gran parte degli altri componenti).
  
- **S4:** ibernazione; lo stato del sistema viene salvato sul disco e il computer può essere quasi completamente spento.
  
- **S5:** sistema spento tramite software, ma ancora collegato all'alimentazione e pronto a essere riacceso tramite eventi come la pressione del pulsante di accensione.

---
[[UEFI (Unified Extensible Firmware Interface)]]
[[BIOS]]
[[Firmware]]