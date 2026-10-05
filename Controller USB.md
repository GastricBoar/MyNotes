---
date: 2024-11-19
tags:
  - informatica
  - pubblico

---
# Controller USB
***
Un controller [[USB (Universal Serial Bus)]] si occupa di gestire la comunicazione tra il computer e i dispositivi USB collegati. È un componente [[Hardware]], proprio un chip fisico sulla scheda madre.  
  
### Come lavora un controller USB?  
Mette a disposizione i protocolli USB per gestire tutto ciò che ci colleghiamo, e lo fa assieme al root hub: un'astrazione logica che instrada i dispositivi verso il controller.  
  
Per fare un esempio:  
  
- colleghi una chiavetta USB 2.0 alla porta USB 2.0  
- il [[Root hub]] rileva un dispositivo collegato alla porta fisica  
- lo segnala al controller  
- il controller riconosce il protocollo USB 2.0 utilizzato dal dispositivo  
- gestisce la comunicazione tramite quel protocollo  
  
Ogni controller USB ha almeno un root hub associato, quindi più controller USB = più root hub.

Qui due scenari:

- alcuni controller implementano più di un protocollo (es. un 2.0, un 3.0 e un 3.1)
  
  <img src="Utilities/Media/Pasted%20image%2020260416214310.png" alt="Pasted image 20260416214310.png" width="586">
  
- diversamente, si associa un controller USB a ogni protocollo, e qui troveresti più controller fisici sulla scheda madre: uno gestisce il protocollo 2.0, uno gestisce il 3.0 e così via.
  
  <img src="Utilities/Media/Pasted%20image%2020260416214343.png" alt="Pasted image 20260416214343.png" width="589">

Su Windows troveresti i root hub utilizzati dal sistema in gestione dispositivi:

<img src="Utilities/Media/Pasted%20image%2020260416214624.png" alt="Pasted image 20260416214624.png" width="613">


***

