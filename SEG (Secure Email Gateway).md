---
date: 2026-09-17
tags:
  - informatica
  - pubblico

---
# SEG (Secure Email Gateway)
---
Sistema di sicurezza che si posiziona tra Internet e il sistema di posta aziendale per analizzare e filtrare le email in entrata e in uscita.

### Come funziona?
Un SEG può presentarsi nella forma di apparato fisico, software su macchina locale, o servizio cloud.

Per fare in modo che le mail da fuori arrivino al SEG hai due opzioni: configuri i record MX del dominio per puntare al SEG invece che al proprio server di posta, oppure (se supportato) utilizzi un'integrazione API per fare accedere il SEG alle mail di quel dominio.

Da lì funziona così:

- Le email da Internet arrivano al SEG.
  
- Lui analizza il messaggio, il mittente, gli allegati e i link presenti nell'email per cercare elementi sospetti.
  
- Se rileva spam, phishing, malware o altre minacce, può bloccare o mettere in quarantena il messaggio.
  
- Se l'email viene considerata sicura, la inoltra al server o al servizio di posta aziendale.

Un SEG può analizzare anche le email in uscita, per esempio per individuare malware o impedire la fuoriuscita di determinate informazioni, quindi uno strumento DLP.

Il termine ESG (Email Security Gateway) viene talvolta utilizzato per indicare la stessa tecnologia, la terminologia varia a seconda del produttore e del contesto.

---