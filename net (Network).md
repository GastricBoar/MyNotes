---
date: 2026-08-03
tags:
  - informatica
  - pubblico

---
# net (Network)
---
Una utility di riga di comando Windows usata per gestire, amministrare e configurare le risorse di rete del sistema, le condivisioni [[SMB]], gli utenti e i servizi locali o di dominio.

È uno strumento legacy ormai.

### net use (Gestire connessioni e unità di rete)
Lanci il comando con la sintassi net use

es.

```cmd
net use Z: \\SERVER-DATI\Condivisa
```

Collega una cartella remota di rete assegnandole una lettera di unità (es. Z:).

oppure, per visualizzare tutte le connessioni di rete attive:

```cmd
net use
```

Senza argomenti, mostra la lista di tutte le risorse di rete e cartelle condivise attualmente connesse.

### net share (Gestire le risorse condivise)
Lanci il comando con la sintassi net share

es.

```cmd
net share CartellaCondivisa=C:\Dati /grant:everyone,full
```

Crea una nuova risorsa condivisa sulla rete partendo da una cartella locale e ne imposta i permessi di accesso.

oppure, per mostrare tutte le condivisioni locali attive:

```cmd
net share
```

Mostra l'elenco di tutte le cartelle, risorse e stampanti condivise sul computer locale.

### net user (Gestire gli utenti locali)
Lanci il comando con la sintassi net user

es.

```cmd
net user Mario Password123! /add
```

Crea un nuovo account utente sul sistema locale assegnandogli una password.

oppure, per visualizzare tutti gli utenti del sistema:

```cmd
net user
```

Elenca tutti gli account utente registrati sulla macchina locale.

### net start / net stop (Gestire i servizi di sistema)
Avvia o arresta un servizio di Windows dalla riga di comando.

Lanci il comando con la sintassi:

```cmd
net stop "Spooler di stampa"
```

I comandi sono spiegati così:
- net start avvia un servizio di sistema specificato (es. net start spooler)
- net stop arresta un servizio di sistema attivo (es. net stop spooler)

### net view (Visualizzare risorse di rete)
Mostra l'elenco dei computer o delle risorse condivise disponibili nella rete locale.

Lanci il comando con la sintassi:

```cmd
net view \\SERVER-DATI
```

Il comando mostra tutte le cartelle e le stampanti condivise pubblicate dal dispositivo remoto specificato.

---
