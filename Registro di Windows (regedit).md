---
date: 2026-06-02
tags:
  - informatica
  - pubblico

---
# Registro di Windows (regedit)
---
Un grosso database binario centralizzato, usato da Windows per memorizzare vari tipi di configurazioni: sistema operativo, associazioni a file, configurazioni software e hardware, impostazioni utenti etc.

### Cosa sono le HKEY?
Ad aprire il registro ti trovi davanti diverse sezioni, iniziano con il prefisso HKEY (Handle to a Registry Key = riferimenti a chiavi di registro):

- **HKEY_LOCAL_MACHINE (HKLM):** contiene configurazioni comuni a tutto il computer, tra cui driver, servizi, hardware e software installato.
  
- **HKEY_CURRENT_USER (HKCU):** configurazioni dell'utente loggato, come sfondo, preferenze, e impostazioni applicazioni.
  
- **HKEY_USERS (HKU):** configurazioni di tutti gli utenti del sistema, ogni utente è identificato da un SID (Security Identifier, tipo S-1-5-18 etc.)

- **HKEY_CLASSES_ROOT (HKCR):** associazioni file, estensioni shell, COM Objects e altro.

- **HKEY_CURRENT_CONFIG (HKCC):** impostazioni su hardware attualmente utilizzato, come monitor, stampanti, profili hardware etc.

Il registro associa a ciascuna chiave dei valori, possono esser binari, testuali, o numerici.

### Dove viene salvato fisicamente?
Nella cartella `C:\Windows\System32\Config` in dei file binari detti hive: SAM, SYSTEM, SOFTWARE, SECURITY, DEFAULT

---