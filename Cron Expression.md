---
date: 2024-10-11
tags:
  - informatica
  - pubblico

---
# Cron expression
---
Una cron expression è una stringa che definisce la pianificazione temporale per eseguire delle operazioni automatiche. La ritroviamo nei sistemi Linux con il comando cron, oppure in Deepser dove può essere utilizzata per pianificare la sincronizzazione dei dati con Active Directory ([[Sincronizzazione Deepser - Active Directory]]).

Una cron expression tipica è composta da 5 o 6 campi, ognuno dei quali rappresenta una parte del tempo, separati da spazi. I campi principali sono:

1. **Minuto** (da 0 a 59)
2. **Ora** (da 0 a 23)
3. **Giorno del mese** (da 1 a 31)
4. **Mese** (da 1 a 12 o nomi dei mesi: `jan`, `feb`, ecc.)
5. **Giorno della settimana** (da 0 a 7, dove 0 e 7 rappresentano la domenica; o nomi dei giorni: `mon`, `tue`, ecc.)

Un possibile campo opzionale: 6. **Anno** (facoltativo, può specificare un anno se necessario).

### Esempi di cron expression

1. **Ogni giorno alle 12:00 (mezzogiorno)**:
    
    `0 12 * * *`
    
    - Significato: alle 12:00 ogni giorno, ogni mese, ogni giorno della settimana.
    
1. **Ogni lunedì alle 8:30 del mattino**:
    
    `30 8 * * 1`
    
    - Significato: alle 8:30 ogni lunedì.
    
1. **Ogni 5 minuti**:
    
    `*/5 * * * *`
    
    - Significato: ogni 5 minuti, ogni ora, ogni giorno.
    
1. **Alla mezzanotte del primo giorno di ogni mese**:
    
    `0 0 1 * *`
    
    - Significato: alla mezzanotte (00:00) del primo giorno di ogni mese.
    
1. **Dal lunedì al venerdì alle 18:00**:
    
    `0 18 * * 1-5`
    
    - Significato: alle 18:00 ogni giorno lavorativo (dal lunedì al venerdì).

---
