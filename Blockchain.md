---
date: 2026-09-15
tags:
  - informatica
  - economia
  - pubblico

---
# Blockchain
---
Tecnologia che permette di mantenere un registro digitale condiviso tra più utenti, senza che sia necessario affidarne la gestione a un'unica autorità centrale.

### Il registro
Immagina te e altri amici, vi vedete spesso e fate continuamente dei piccoli pagamenti tra di voi. Per esempio:

- Stasera andate a cena e paghi il conto per tutti, domani Marco paga una pizza, dopodomani Luca compra i biglietti del cinema.
  
- Dopo un po' diventa un casino ricordarsi chi debba soldi a chi.
  
- Invece di scambiarvi soldi ogni volta, create un registro comune sul web, è semplicemente una lista che tiene traccia dei pagamenti in stile "Marco > Luca: 20 euro; Luca > Paolo: 40 euro".

- A fine mese potete prendere questo elenco e fare i conti.

Adesso arriva il primo problema: il registro comune sta su un sito web pubblico, tutti possono aprirlo e aggiungere una riga. Io posso scrivere "Marco > Luca: 20 euro", ma chi impedisce a Luca di scrivere "Marco > Luca: 1000 euro" senza il mio permesso?

### La firma digitale
Abbiamo il nostro registro pubblico, ma per come dicevamo: come faccio a sapere che Marco ha davvero autorizzato "Marco > Luca: 1000 euro"?

Ci serve qualcosa che permetta a Marco di dimostrare di aver autorizzato quel pagamento, senza che gli altri possano falsificarla; per esempio, una firma.

Pensando alle firme che facciamo con carta e penna, servono a comunicare "questo documento è approvato da me", ma c'è un problema: una firma su carta è sempre la stessa, e se qualcuno riesce a copiarla può provare a metterla su un altro documento. 

Non va bene, quindi pensiamo a un'altra cosa: la firma digitale. Funziona così:

- Marco genera due chiavi digitali: una pubblica e una privata.
  
- La chiave privata deve essere custodita in massima segretezza da Marco.
  
- La chiave pubblica invece può essere conosciuta da tutti.
  
- Marco vuole autorizzare la transazione "Marco > Luca: 20 euro".
  
- Usa la sua chiave privata per creare una firma digitale di quella specifica transazione, il processo è "Marco > Luca: 20 euro" più chiave privata, è uguale a firma digitale.

- Pubblica quella firma insieme alla transazione, quindi nel registro vediamo Marco > Luca: 20 euro" e firma associata "10111000111010101011..."
  
- Se qualcuno vuole verificare l'autenticità di quella transazione, prende la chiave pubblica, la firma digitale associata alla transazione e usa una funzione di verifica.

- Se la funzione restituisce esito "Valida" allora la firma è stata prodotta dalla chiave privata di Marco e corrisponde esattamente a quel messaggio. Allo stesso tempo, se qualcuno modifica anche solo una parte del messaggio, la firma originale non è più valida.

Abbiamo risolto il problema della falsificazione, perchè Luca non può scrivere  "Marco > Luca: 20 euro" senza che Marco lo sappia, ma spunta un'altro problema: chi impedisce a Luca di copiare quella transazione 50 volte per fregarsi 1000 euro? 

### La doppia spesa (double spending)
Marco ha verificato la transazione "Marco > Luca: 20 euro", ma cosa è una transazione se non un oggetto digitale? il problema è questo:

- Se io ti do una banconota da 20 euro, la sto togliendo dalla mia tasca e mettendo nella tua; io passo dall'avere una banconota all'avere zero banconote, e tu passi dall'avere zero banconote all'avere una banconota.
  
- Gli oggetti digitali però non funzionano così: se ti invio una foto la sto duplicando, avevo una foto e continuo ad averla, tu ricevi una foto, quindi adesso siamo in due ad avere una foto. 
  
- Luca prende quindi la transazione firmata da Marco, e la copia. Adesso Luca ha 50 transazioni che attestano "Marco > Luca: 20 euro". 

Questa si chiama doppia spesa (double spending), e quello che tocca risolvere adesso è "Come faccio a impedire che la stessa transazione venga copiata e riutilizzata"?

### L'identificativo univoco della transazione (Transaction ID)
Per evitare che una transazione firmata possa essere semplicemente riutilizzata ovunque, dobbiamo fare in modo che ogni pagamento sia unico e distinguibile da tutti gli altri.

Allora si fa così: 

- Ogni transazione riceve un identificativo univoco, e Marco ne inserisce uno all'interno della sua transazione.

- La transazione diventa quindi "ID: 847291 — Marco > Luca: 20 euro".
  
- Se Luca copia 50 volte la transazione, sarà palese la disonestà del suo gesto.

Sorge un'altro problema ancora: come facciamo a sapere che Marco non sta spendendo più soldi di quanti ne possegga?

### La storia delle transazioni
Mettiamo Marco sia partito con un budget di 100 euro: ne ha dati 20 a Luca con una transazione che è adesso sia unica che verificata, ma chi gli impedisce di creare una transazione da altri 200 euro per Anna? alla fine anche quella sarebbe unica e verificata, no?

Ci serve a questo punto un modo per verificare che Marco non stia spendendo più di quanto abbia a disposizione, perchè per accettare una transazione non basta più verificare che sia unica e firmata.

Allora facciamo così:

- Rileggiamo a ritroso la storia del registro, la cronologia delle transazioni.
  
- Se Marco ha dato 20 euro a Luca durante la prima transazione, lui ne ha 80 e Luca ne ha 120; non può quindi darne 200 ad Anna.
  
- Il registro non è più una semplice lista di pagamenti: adesso determina quanto possiede ciascun partecipante e quali sono le transazioni future valide.

Di nuovo un problema: finora abbiamo parlato di euro reali, che alla fine del mese qualcuno deve effettivamente consegnare nelle mani di un'altra persona.

### La moneta digitale (criptovalute)
Finora il nostro registro ha detto cose come "Marco > Luca: 20 euro", ma quegli euro esistono al di fuori del registro, e lui sta solo tenendo traccia di quanto, alla fine del mese, le persone dovrebbero effettivamente scambiarsi.

E se volessimo eliminare completamente la dipendenza dal denaro fisico? facciamo un'altro passo ancora:

- Diamo alle unità registrate nel registro un loro nome: le PizzaCoin.
  
- Le PizzaCoin non rappresentano più un euro reale che qualcuno deve consegnare a qualcun altro, sono una moneta autonoma, interna al sistema, la loro esistenza dipende dal registro e dalle sue regole, non da banconote fisiche.
  
- Ovviamente potrebbe comunque succedere che Marco si accordi con Luca per scambiare euro con PizzaCoin (es. Marco dà 10 euro a Luca, e Luca registra 10 PizzaCoin a favore di Marco) ma questo scambio non è che sia garantito dalle regole del nostro sistema, è solo un accordo tra persone.

Il nostro registro è passato dall'essere un sistema che ci ricorda chi deve euro a chi, all'essere lui stesso quello che definisce una moneta digitale.

Restano ancora problemi però.

### Il registro distribuito
Il nostro registro è stato ospitato su un sito web, però c'è un grosso elefante nella stanza: chi lo gestisce quel sito?

Il problema del sito web è proprio che, nonostante sia pubblico, ci stiamo ancora affidando a qualcuno. Quella persona potrebbe decidere quali transazioni accettare, modificare o cancellare transazioni, mostrare una versione diversa del registro a persone diverse, o semplicemente spegnerlo di colpo.

È un punto centrale di fiducia, troppo fragile per essere affidabile; la soluzione è:

- Facciamo in modo che non esista una sola copia del registro, diffondiamo una copia a ogni partecipante della rete.
  
- Se Marco vuole pagare a Luca 20 PizzaCoin, non manda la richiesta a un unico sito centrale, ma la diffonda a tutta la rete in modo che gli altri partecipanti possano registrarla nella propria copia.

Adesso non c'è più una persona che possiede l'unica copia del registro potendo modificarla a piacimento, ma abbiamo creato un problema nuovo: se ognuno ha una propria copia del registro, come facciamo a fare in modo che tutti abbiano la stessa versione?

### Il consenso distribuito
Marco ha un saldo di 20 PizzaCoin, e invia contemporaneamente due transazioni: "Marco > Luca: 20 PizzaCoin" e "Marco > Anna: 20 PizzaCoin"; non può farlo! ne possiede solo 20, allora quale delle due deve essere accettata? chi lo decide?

La risposta sarebbe stata "lo decide il proprietario del sito", ma il proprietario del sito non esiste più perchè il registro appartiene a tutti adesso. Pensando:

- Non potendo più fare affidamento a un registro centrale, dobbiamo fidarci di una regola: ma quale?

- Per buttare un'idea potremmo dire "Facciamo votare, e chi prende più voti decide; sarà la maggioranza a decidere".

- Per fare votare serve stabilire chi può votare e quanto vale il voto di ciascuno.

- Il problema è che così diventa facile barare: uno dei partecipanti potrebbe creare migliaia di identità per ricevere migliaia di voti e falsificare la maggioranza.
  
- Ci serve qualcosa di diverso allora: una proprietà che è difficile da ottenere ma facilmente verificabile da tutti.
  
- Il lavoro computazionale è perfetto per questo compito, perchè data una certa sfida è una risorsa costosa da produrre; la regola passa da "vince la versione che ha ricevuto più voti" a "vince la versione che dimostra di aver prodotto più lavoro computazionale".
  
### Proof of work
Scegliere la produzione di lavoro computazionale come metro per il nostro consenso distribuito è un sistema più solido rispetto a contare un certo numero di voti: tu puoi anche creare 10.000 identità se vuoi, ma per influenzare la scelta devi comunque produrre il lavoro computazionale necessario. Questa si chiama "proof of work", e nel pratico si fa così:

- Prendiamo un gruppo di transazioni tipo "Marco > Luca: 20 PizzaCoin" e "Luca > Anna: 10 PizzaCoin".
  
- Scegliamo un nonce, che è un numero casuale tipo 847291.
  
- Mettiamo insieme transazioni e nonce.
  
- Usiamo un algoritmo di hashing (ogni criptovaluta ne può scegliere uno diverso eh) per calcolare l'hash di quella combinazione.
  
- Adesso abbiamo un hash, ma non basta calcolare un hash qualsiasi per dimostrare di aver lavorato; dobbiamo quindi inventarci una condizione precisa che l'hash deve rispettare.
  
- Per esempio, potremmo stabilire che l'hash prodotto dalle transazioni più nonce deve iniziare con 30 zeri, che è una condizione difficile da ottenere e ci richiede di ricalcolare hash con tantissimi nonce diversi.
  
- Se riesci a trovare un hash che rispetti quella condizione, hai prodotto una proof of work valida per quel gruppo di transazioni.
  
- Produrre quell'hash è un lavoro faticoso, ma è invece facilissimo verificarlo al contrario, perchè basta elaborare l'hash del gruppo di transazioni più il nonce giusto trovato.

### I blocchi e i miner
Abbiamo un gruppo di transazioni per cui qualcuno è riuscito a trovare una proof of work valida. Quello che succede adesso è:

- Impacchettiamo il gruppo di transazioni, il nonce, e l'hash risultante in un'unica struttura chiamata "blocco".
  
- Il partecipante che ha trovato la proof of work trasmette il blocco alla rete, perchè vuole che gli altri partecipanti lo riconoscano e lo aggiungano alla propria copia del registro.
  
- I partecipanti che cercano proof of work si chiamano miner.

I blocchi possono contenere un numero limitato di transazioni: la quantità di dati che ciascun blocco può contenere è limitata dalle regole della blockchain. Non ci sta una dimensione fissa come "un blocco contiene 2.000 transazioni", dipende da quanto sono grandi le singole transazioni, e nel caso di Bitcoin il protocollo usa il block weight come unità di misura, per un limite massimo di 4 milioni di weight units (WU).
  
### Collegare i blocchi tra loro
Quando qualcuno produce un blocco valido, lo trasmette agli altri, che lo aggiungono alla propria copia del registro. Però immagina questo: Marco riesce a modificare una transazione contenuta in un vecchio blocco, prende il blocco 1 e la transazione "Luca > Marco: 20 Pizzacoin" diventa "Luca > Marco: 2000 PizzaCoin".

La rete potrebbe verificare la transazione modificata, ma non avrebbe modo per capire, guardando i blocchi successivi, che il contenuto del vecchio blocco è stato cambiato. La domanda diventa "Come impediamo a qualcuno di modificare una parte vecchia del registro senza che la rete se ne accorga?", e la soluzione è questa:

- Dobbiamo fare in modo che ogni blocco dipenda dal contenuto del blocco precedente.
  
- Per ogni blocco prodotto, inseriamo allora l'hash del blocco precedente; per esempio, l'hash del blocco 2 contiene anche l'hash del blocco 1. Questa è la "catena" dei blocchi, dal quale ci arriva il nome "blockchain".
  
- Se Marco modifica il blocco 1, cambia il suo hash.
  
- Il blocco 2 però contiene ancora l'hash del "vecchio" blocco 1, che non corrisponde all'hash del blocco 1 modificato da Marco.
  
- Se Marco vuole rendere la cosa leggittima, dovrebbe ricalcolare la proof of work del blocco 2, poi del blocco 3, poi del blocco 4 e così via.
  
### Il 51% attack
Ricalcolare quei blocchi non è matematicamente impossibile, ma è computazionalmente proibitivo. Ricostruire privatamente una propria versione della block chain è così difficile per due motivi:

- Marco dovrebbe recuperare tutto il lavoro che la rete ha già prodotto.
- Allo stesso tempo, dovrebbe continuare a tenere il passo con il nuovo lavoro prodotto dalla rete onesta.

Sai come Marco riuscirebbe a sostenere questa mole di lavoro enorme? controllando più del 50% della potenza di hashing complessiva della rete; così facendo, riuscirebbe a produrre blocchi più velocemente di tutti gli altri messi insieme.

### I fork e la catena più lunga
Abbiamo un nuovo problema da risolvere adesso:

- Supponiamo che due miner trovino quasi contemporaneamente una proof of work valida per due blocchi diversi; sono entrambe corrette, e una divisione della catena prende il nome di "fork" con diversi sotto-tipi.
  
- Allora come facciamo a far tornare la rete su un'unica versione condivisa?
  
- La regola qui è "quando ci sono più catene valide, la rete considera quella su cui è stato accumulato più lavoro computazionale".
  
- Quello descritto su è un fork temporaneo, perchè la rete ha temporaneamente due rami; quando verrà prodotto un nuovo blocco, la rete convergerà di nuovo sul ramo che ha accumulato più lavoro.

### Il tempo di produzione dei blocchi
Se la proof of work consiste nel provare continuamente nonce diversi finché non troviamo un hash che soddisfa una certa condizione, possiamo rendere il problema più o meno difficile cambiando quella condizione. Trovare un hash che inizi con 3 è facile, trovarne uno con 40 è più difficile.

Adesso pensa: oggi abbiamo 100 miner e domani ne abbiamo 1.000 o l'hardware si fa sempre più capace nel tempo. Qui si pone il problema "se la potenza di calcolo dei miner aumenta, la rete potrebbe iniziare a produrre blocchi sempre più velocemente", il che potrebbe essere non desiderabile per vari motivi:

- La rete avrebbe meno tempo per diffondere e verificare i nuovi blocchi.
  
- Aumenterebbero le situazioni in cui due miner trovano quasi contemporaneamente un blocco, quindi i fork temporanei.
  
- Cambierebbe il ritmo con cui il sistema aggiunge nuove unità di valuta e conferma le transazioni.

Ogni criptovaluta sceglie il proprio ritmo di produzione: Bitcoin punta a produrre un blocco ogni 10 minuti, Dogecoin ogni minuto, Kaspa ogni 0,1 secondi. Non è che siano leggi della fisica, Bitcoin punta a 10 minuti, ma potresti ritrovarti due blocchi a distanza di pochi secondi oppure un'attesa più lunga. In generale, la difficoltà viene regolata per mantenere il tempo medio di produzione vicino al target scelto dalla blockchain.

### Le block reward
I miner spendono risorse computazionali (elettricità, hardware) e competono per produrre nuovi blocchi, ma chi glielo fa fare? perchè dovrebbero?

Qui il sistema introduce una ricompensa per chi produce un blocco valido: chi produce un blocco prende una certa quantità di una valuta, così che siano incentivati a produrre nuovi blocchi.

Fin adesso avevamo stabilito che per effettuare una transazione bisogna possedere PizzaCoin, trasferite da un partecipante all'altro, ma non avevamo previsto nessun meccanismo per il quale nuove PizzaCoin potessero entrare nel sistema. 

Il metodo ufficiale allora è che i miner possano inserire nel blocco prodotto una transazione speciale, la coinbase transaction, che assegna a sè stesso una certa quantità di nuove PizzaCoin.

### Le commissioni di transazione
Abbiamo già visto che il miner riceve una block reward, ma c'è un secondo modo con cui può essere ricompensato: le commissioni di transazione.

Quando Marco vuole effettuare una transazione, può includere una piccola quantità di PizzaCoin come commissione destinata al miner che includerà quella transazione in un blocco. A quanto ammonta la transazione? questo c'è un ragionamento da fare, che ritorna alla capacità limitata dei blocchi:

- Mettiamo che alla rete arrivino 10.000 transazioni, ma che il blocco in costruzione ne possa contenere solo una parte.
  
- Il miner deve scegliere quali transazioni inserire.

- Si crea un mercato delle commissioni attorno a questa cosa, perchè più persone vogliono entrare nello stesso blocco, più competono offrendo commissioni, più i miner hanno un incentivo a includere con priorità le transazioni con le commissioni più interessanti.

Le commissioni diventano quindi un meccanismo per decidere quali transazioni vengono incluse quando lo spazio disponibile non basta per tutti.

### L'offerta massima e l'halving
Se permettiamo ai miner di creare nuove PizzaCoin ogni volta che producono un blocco, dobbiamo stabilire secondo quali regole vengono create le nuove monete; se un miner potesse semplicemente arrivare e dire "adesso mi assegno 1 miliardi di PizzaCoin" la moneta perderebbe il senso costruito finora.

Una delle possibilità è stabilire un'offerta massima (maximum supply), un tetto alla quantità totale di monete che potranno mai esistere. Per esempio, Bitcoin è limitato a 21 milioni, Litecoin a 84 milioni e Cardano a 45 miliardi. 

Non è che sia obbligatorio avere un'offerta massima: Dogecoin, per esempio, continua a creare nuove monete come ricompensa per i blocchi e non ha un limite massimo prefissato. Questo non significa però che i miner possano creare quante monete vogliono: la quantità di nuove monete creata è comunque stabilita dalle regole del protocollo.

Per alcune criptovalute, la ricompensa per i miner viene ridotta tramite l'halving, un meccanismo che periodicamente dimezza la ricompensa, rallentando la creazione di nuove monete nel tempo; per esempio: in Bitcoin la ricompensa è passata da 50 BTC nel 2009 a 25 nel 2012, 12,5 nel 2016, 6,25 nel 2020 e 3,125 nel 2024. Lì ogni halving avviene dopo 210.000 blocchi, ogni quattro anni circa.

Si stima che la ricompensa derivante dalla creazione di nuovi Bitcoin sia progettata per arrivare a zero intorno al 2140. A quel punto i miner continueranno a produrre nuovi blocchi per le transazioni degli utenti, ma non verranno più creati nuovi Bitcoin come ricompensa del blocco: riceveranno solo le commissioni pagate dagli utenti per le transazioni incluse nei blocchi.

### A cosa serve?
La blockchain è particolarmente utile quando più partecipanti devono condividere un registro e vogliono poter verificare che le informazioni non siano state alterate.

Viene utilizzata, per esempio, per:

- Criptovalute (Cryptocurrency) come Bitcoin ed Ethereum.
  
- Contratti intelligenti (Smart Contract), cioè programmi che vengono eseguiti sulla blockchain secondo regole prestabilite.
  
- Tracciamento e gestione di asset digitali (Digital Assets), come token e NFT.
  
- Applicazioni decentralizzate (dApp), cioè applicazioni il cui backend può essere costituito da smart contract eseguiti su una rete blockchain.

---