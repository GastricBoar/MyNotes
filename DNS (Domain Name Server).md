---
date: 2024-12-31
tags:
  - informatica
  - pubblico

---
# DNS (Domain Name Server)
***
Un sistema che traduce nomi di dominio ([[FQDN (Fully Qualified Domain Name)]]) in indirizzi IP.

I DNS sostituiscono il vecchio [[Host file]].
##### **I DNS server nel mondo**
I DNS server globali sono organizzati su una scala gerarchica:

![Pasted image 20250102175706.png](Utilities/Media/Pasted%20image%2020250102175706.png)

Analizziamoli uno ad uno:

- **Root servers:** dei super-server che si occupano del dominio "."
- **Domini di primi livello:** come ".com" o ".it"
- **Domini di secondo livello:** come il "google" nel dominio "google.com"
- **DNS server interno:** può essere interno al nostro PC, o ereditato da un server [[DHCP (Dynamic Host Configuration Protocol)]].
- **Host file:** [[Host file]].
###### **Come viene risolto un dominio?**
Metti di voler risolvere un dominio tipo www.google.com; Tenendo a mente che il tuo PC legge il dominio da destra a sinistra, ecco come fare:

1. Il sistema controlla all'interno del proprio host file o della propria cache.
2. Se non trova corrispondenza, consulta il DNS interno o interno al DHCP.
3. Se non trova corrispondenza, il DNS server interno può comunque aiutarci; in questo caso, localizza il root server più vicino al nostro dispositivo.
4. Il root server non conosce la risoluzione intera di www.google.com, ma conosce dove si trova il server di primo livello che si occupa di risolvere quel ".com"; ti reindirizza lì.
5. Il server che contiene i domini di primo livello scarica di nuovo il barile, perchè non sa come risolvere il dominio di secondo livello "google"; ti reindirizza al server che contiene i domini di secondo livello.
6. Il server che contiene i domini di secondo livello trova finalmente l'indirizzo IP corretto, e te lo invia.
###### **Perchè alcuni domini vengono risolti immediatamente, mentre altri ci mettono un po'?**
Perchè viene tenuta una copia in cache di quella risoluzione, internamente nel tuo DNS server . Non solo, ma se ti affidi a un server DHCP, vengono tenute in cache tutte le risoluzioni che son passate per quel server entro un determinato limite temporale.

###### **Ma come faccio ad associare un nome di dominio al mio server?**
Non puoi farlo in autonomia, queste cose costano e si pagano:

1. **Acquista il dominio:** da un registrar accreditato, come Aruba, GoDaddy, Namecheap, Google Domains.

2. **Configura i [[Record DNS]]:** di questo se ne può occupare il registrar stesso, oppure un servizio DNS esterno (per esempio Cloudflare, AWS Route 53 o Google Cloud DNS). 
***
[[Indirizzo IP (Internet Protocol)]]

Il comando [[nslookup (Name Server Lookup)]] si usa per far troubleshooting su un server DNS, in pratica verifica che sia attivo e funzionante.
