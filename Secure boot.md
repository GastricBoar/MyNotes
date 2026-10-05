---
date: 2026-04-16
tags:
  - informatica
  - pubblico

---
# Secure boot
---
Una delle funzioni di [[UEFI (Unified Extensible Firmware Interface)]], impedisce l'esecuzione di software non autorizzato all'avvio del PC.

Per fare un esempio: qualcuno modifica il tuo bootloader, un malware potrebbe aver controllo del tuo PC ancora prima che l'antivirus parta da sistema operativo.

### Come funziona?
Tramite un sistema di chiavi crittografiche: creano una firma digitale del firmware necessario all'avvio, e se qualcosa cambia ne impedisce l'avvio.

Ci sono dei casi in cui potresti volerlo disattivare, come alcuni software per live USB e alcune distro [[Linux]].

---
[[Crittografia]]