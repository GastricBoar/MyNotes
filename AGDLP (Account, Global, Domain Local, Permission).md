---
date: 2026-06-03
tags:
  - informatica
  - pubblico

---
# AGDLP (Account, Global, Domain Local, Permission)
---
Un modello Microsoft di gestione permessi Active Directory, è una serie di consigli per gestire ruoli e accesso alle risorse in maniera scalabile all'interno di un dominio.

### Che significa quell'acronimo?
Scomponendolo per pezzi:

- **Account:** i singoli utenti (Mario, Luca, Sara, Alessia etc.)
  
- **Global:** i gruppi global rappresentano l'identità dell'utente, il suo ruolo o reparto (es. GG_Contabilità, GG_Marketing, GG_IT etc.); rispondono alla domanda "chi sei"
  
- **Domain Local:** i gruppi domain local rappresentano una specifica autorizzazione (es. DL_Marketing_RW, DL_Amministrazione_RO etc.); rispondono alla domanda "cosa puoi fare"
  
- **Permission:** il permesso associato al gruppo domain local (es. Modify al gruppo DL_Marketing_RW).

### Un esempio
Per capire meglio come funziona, partiamo da un esempio che non usa AGDLP:

- Hai un server sul quale ospiti una share di rete `\\fileserver\Share Contabilità`
  
- Anna, Marco e Paolo del reparto contabilità ti chiedono di accederci
  
- Crei un gruppo chiamato "Contabilità" e ci metti dentro Anna, Marco e Paolo
  
- Assegni il permesso RW su quella cartella per il gruppo
  
- Nel tempo crei altre 100 cartelle al quale l'ufficio contabilità accede
  
- L'azienda acquista una società esterna con 20 dipendenti

- Queste persone hanno bisogno di accedere alle share di rete con il quale lavora la contabilità, e sono molte

- A te tocca creare il gruppo "Studio Paghe" e assegnare permessi per tutte le cartelle a cui accede l'ufficio contabilità, uno a uno
  
Adesso, ripensala con AGDLP:

- Crei un gruppo DL_Share_Contabilità_RW
  
- Ci metti dentro il gruppo GG_Contabilita
  
- Assegni al gruppo DL il permesso Modify per la cartella 
  
- Quando il nuovo ufficio ti chiede accesso a quelle cartelle, ti basta aggiungere il gruppo GG_StudioPaghe al gruppo DL_Share_Contabilità_RW

### Un paio di osservazioni
AGDLP è scalabile perché separa "chi è cosa" da "chi fa cosa", però ci sono delle considerazioni da fare.

### AGDLP non elimina la necessità di progettare correttamente i permessi
Se due gruppi di persone devono accedere a risorse diverse, sarà comunque necessario creare gruppi Domain Local differenti:

- Hai una share: `\\fileserver\Contabilità`

- Al suo interno sono presenti bilanci, stipendi, fatture
  
- L'ufficio Contabilità deve accedere a tutto
  
- Lo Studio Paghe deve accedere solo alla cartella Stipendi
  
- Non puoi usare un unico gruppo `DL_Contabilita_RW`

- Devi creare gruppi più specifici: DL_Bilanci_RW, DL_Stipendi_RW, DL_Fatture_RW

### AGDLP non risolve i problemi di classificazione dei dati
Se gli utenti salvano documenti sensibili in cartelle accessibili a molte persone, il problema non è Active Directory ma l'organizzazione dei dati.

- L'ufficio Contabilità ha accesso a `\\fileserver\Contabilità`

- Un dipendente crea `\\fileserver\Contabilità\NuovoProgetto`

- Ci salva dentro stipendi, contratti e dati fiscali

- La cartella eredita automaticamente i permessi della share
  
- Tutte le persone che avevano accesso alla share possono accedere anche a questi documenti
  
- AGDLP non può sapere che quei documenti avrebbero dovuto essere protetti, e a meno che un responsabile non lo chieda all´IT allora resteranno visibili a tutti

### Non è necessario creare un gruppo Domain Local per ogni cartella
Nella pratica si creano gruppi che rappresentano autorizzazioni per aree ben definite, non troppo specifiche (a meno che non siano sensibili)

- Gli utenti creano:

```text
\\fileserver\Contabilità\2024
\\fileserver\Contabilità\2025
\\fileserver\Contabilità\Fatture
\\fileserver\Contabilità\Archivio
```

- Tutte le cartelle devono essere accessibili alle stesse persone
  
- Non serve creare DL_2024_RW, DL_2025_RW, DL_Fatture_RW, DL_Archivio_RW

- È sufficiente utilizzare DL_Contabilita_RW

- Le sottocartelle erediteranno automaticamente i permessi, e l'amministratore interviene solo in caso servano specifiche restrizioni

### Il vantaggio di AGDLP si nota soprattutto in ambienti grandi
In un piccolo ufficio con pochi utenti e poche share, assegnare direttamente i gruppi Global ai permessi può essere sufficiente.

- Una piccola azienda ha 10 utenti, 2 reparti, 3 share

- Gli ACL potrebbero essere: GG_Contabilita > Modify e GG_HR > Modify

- La gestione è semplice e probabilmente non crea problemi

- Una grande azienda ha 500 utenti, 20 reparti, 200 share

- Modificare continuamente gli ACL delle risorse diventa più complesso

### AGDLP non serve tanto a ridurre il numero di gruppi
Serve a centralizzare la gestione degli accessi.


---