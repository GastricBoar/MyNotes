---
date: 2026-02-16
tags:
  - informatica
  - pubblico

---
# Bitlocker
---
Il sistema di [[Crittografia]] integrato in Windows.

### **Come funziona?**
Lo usi per proteggere i tuoi dati in caso di furto fisico del tuo PC. L'intero contenuto del tuo disco viene cifrato tramite un algoritmo (AES); se qualcuno prova a leggerne il contenuto senza autorizzazione, vede solo dei dati incomprensibili.

Quando abiliti Bitlocker ti viene generata una chiave di ripristino (recovery key) da 48 cifre. Questa chiave qui ti permette di recuperare l'accesso al disco in caso di modifiche hardware o firmware.

Puoi proteggere lo sblocco del disco in diversi modi:

- **Custodito da un chip [[TPM (Trusted Platform Module)]]:** se nessuno dei componenti critici di sistema è stato modificato, il disco viene sbloccato.
  
- **Protetto da password o PIN all'avvio:** ti viene chiesta a ogni avvio; se corretta, il disco viene sbloccato.
  
- **Utilizzo di una chiavetta USB (startup key):** se collegata al PC, il disco viene sbloccato.

---
