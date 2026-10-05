---
date: 2024-12-16
tags:
  - informatica
  - pubblico

---
# Cambiare layout di tastiera da CLI Linux
---
1. **`sudo dpkg-reconfigure keyboard-configuration`:** Ti guida nella riconfigurazione del layout della tastiera.
2. Seleziona il layout preferito dal wizard.
3. **`sudo service keyboard-setup restart`:** Applica le modifiche senza riavviare il sistema.
4. **`localectl status`:** Mostra il layout attuale della tastiera e altre impostazioni di localizzazione.

---
