---
date: 2026-02-17
tags:
  - informatica
  - pubblico

---
# UPS (Uninterruptible Power Supply)
---
Un dispositivo che fornisce alimentazione elettrica temporanea a ciò che ci è collegato, proteggendoli da blackout e sbalzi di tensione.

### **Come funziona?**
Il contesto è questo: la rete elettrica non è perfetta, e i dispositivi elettronici possono essere delicati.

In Italia la corrente elettrica domestica ci fornisce una tensione di 230 Volt a una frequenza di 50 Hertz in [[AC (Corrente Alternata)]]. In teoria è costante, ma nella pratica la corrente che ci arriva può esser "sporca": succedono cose tipo cali di tensione (sags o brownouts), picchi di tensione (spikes o surges) e micro-interruzioni.

Ecco, un UPS fa generalmente due cose:

- **ti garantisce continuità elettrica:** salva dai blackout, la batteria interna entra in funzione e garantisce qualche minuto extra di continuità elettrica al tuo dispositivo; non è molto, ma ti permette di spegnere il sistema in modo ordinato.
  
- **stabilizza la tensione:** protegge il dispositivo dalla corrente "sporca" compensa i cali di tensione, filtra i picchi di tensione, gestisce le micro-interruzioni.


### **Le categorie di UPS**
Tre categorie, in base a quello che serve:

| Tipo di UPS                 | Tempo di commutazione | Stabilizza tensione | Efficienza energetica | Costo | Uso tipico           |
| --------------------------- | --------------------- | ------------------- | --------------------- | ----- | -------------------- |
| Offline (Standby)           | Sì                    | No                  | Alta                  | Basso | PC domestici         |
| Line-Interactive            | Sì                    | Sì                  | Buona                 | Medio | Workstation / NAS    |
| Online (Doppia conversione) | No                    | Sì                  | Inferiore             | Alto  | Server / Data Center |

### **Che è il tempo di commutazione?**
Durante un'interruzione di corrente, ci sta un intervallo di tempo da qualche millisecondo in cui l'UPS si accorge di non star più ricevendo tensione, e passa in modalità batteria (la batteria DC comincia a produrre corrente AC). Si chiama tempo di commutazione, e se è troppo lungo il PC si spegne.

Adesso, l'alimentatore riesce a trattenere della corrente nei propri condensatori per qualche millisecondo, si chiama hold-up time; il tempo di commutazione di un buon UPS nuovo è più basso di quel tempo lì, quindi va bene così.

Pensa però a un data center critico dove non potresti permetterti quel rischio, è lì che gli UPS Online sono importanti: gli UPS online hanno una catena di corrente che:

1. Riceve corrente AC dalla presa a muro.
2. La converte in DC per mantenere carica la batteria.
3. La ritrasforma in AC, che alimenta costantemente il dispositivo.

Questa catena azzera i tempi di commutazione, il dispositivo è collegato alla corrente AC dall'inizio. 

Comunque alla fine di questo viaggio, il [[PSU (alimentatore)]] riconverte la corrente AC in DC, per farla arrivare a ciascun componente con la giusta tensione elettrica.

---
[[Come funziona la rete elettrica]]