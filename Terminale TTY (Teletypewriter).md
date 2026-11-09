---
date: 2026-11-06-22-57
tags:
  - informatica
  - pubblico
  - linux
---
# TTY (Teletypewriter)
---
Interfaccia testuale che permette all'utente di interagire con il sistema operativo tramite comandi, senza utilizzare un'interfaccia grafica.

### La storia
Negli anni '50 e '60 i PC erano grandi macchinari installati in apposite sale; queste macchine non avevano necessariamente degli schermi integrati.

<img src="Utilities/Media/Pasted%20image%2020261106232123.png" alt="Pasted image 20261106232123.png" width="537">

Siccome a più persone serviva interagire con queste macchine, si diffusero i terminali: dispositivi con tastiera e schermo separati dalla macchina centrale.

Lo scenario era quindi questo: tu sedevi davanti al terminale, usavi la tastiera per inviare comandi al computer centrale, e lo schermo per visualizzare le risposte che quel computer ti restituiva.  

Qui in foto il DEC VT100:

<img src="Utilities/Media/Pasted%20image%2020261106232438.png" alt="Pasted image 20261106232438.png" width="357">

### Gli emulatori di terminale
Con il tempo, i computer cominciarono a integrare direttamente schermo, tastiera e interfaccia grafica; non era più necessario utilizzare un terminale fisico separato, potevi semplicemente usare un'applicazione che ne riproducesse il funzionamento all'interno di una finestra desktop: si chiama emulatore di terminale.

Esempi di emulatore di terminale sono Ghostty, Kitty, Alacritty, o Konsole.

### La shell
L'emulatore di terminale ci permette di interagire con il computer attraverso un'interfaccia testuale, ma abbiamo bisogno di qualcuno che interpreti quello che scriviamo: se apri Ghostty e scrivi `ls`, lui riceve i caratteri e li mostra nella finestra, ma nel pratico non sa cosa significhi quel comando.

Quel qualcuno è un programma: la shell, che riceve le istruzioni dell'utente, le interpreta e avvia i programmi necessari. Sono esempi di shell: Bash, Zsh e Fish.

### Lo pseudo-terminale (PTY)
Abbiamo visto che l'emulatore di terminale gestisce l'interfaccia grafica, mentre la seconda interpreta i comandi, ma come fanno a comunicare tra loro? tramite uno pseudoterminale.

Uno pseudoterminale è un dispositivo virtuale che permette a emulatore di terminale e shell di scambiarsi input e output come fossero collegati a un terminale fisico: quando digiti un comando, i caratteri vengono trasmessi alla shell attraverso il PTY, e viceversa, quando la shell produce un risultato, torna attraverso il PTY all'emulatore, che lo visualizza nella finestra.

### Ma perchè scegliere un emulatore di terminale?
Se l'emulatore di terminale svolge un'attività così semplice, allora che senso ha scegliere Ghostty, o Kitty, o la rava e la fava?

Il punto è che la parte difficile del lavoro dell'emulatore di terminale non è mostrare del testo in finestra, ma molto altro:

- **Le prestazioni:** visualizzare migliaia di righe al secondo, aggiornare contenuti continuamente, gestire più sessioni; un emulatore deve elaborare questi dati senza diventare lento.

- **Le funzionalità avanzate:** dividere la finestra in più sessioni, visualizzare immagini nel terminale, personalizzare font, colori, scorciatoie, configurazioni.
  
  <img src="Utilities/Media/Pasted%20image%2020261106235101.png" alt="Pasted image 20261106235101.png" width="428">

- **La compatibilità:** i programmi possono inviare al terminale sequenze di controllo per chiedere di spostare il cursore, cambiare colore al testo, cancellare una porzione di schermo e così via; gli emulatori devono interpretare queste sequenze, un emulatore moderno deve supportare comportamenti diversi senza rompere la compatibilità con quelli tradizionali.

---
