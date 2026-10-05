---
date: 2025-01-02
tags:
  - informatica
  - pubblico

---
# Record DNS
***
Istruzioni memorizzate e distribuite al mondo dai server [[DNS (Domain Name Server)]].

Questi records specificano come il nome di dominio punta a un servizio, che può essere un [[Indirizzo IP (Internet Protocol)]] per un sito web oppure un server di posta per e-mail.

##### **Tipi di record DNS**

###### **A record (Address record)** 
Punta un dominio a un indirizzo IPv4. Per esempio:

```
miosito.com    A    192.168.1.1
```

###### **AAAA Record (Quad-A Record)** 
Punta un dominio a un indirizzo IPv6. Per esempio:

```
miosito.com    AAAA    2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

###### **CNAME Record (Canonical Name Record)**
Fa di un dominio un alias per un altro dominio, in modo che chi visita il primo dominio verrà reindirizzato ad un altro. Per esempio:

```
www.miosito.com    CNAME    miosito.com
```

###### **MX Record (Mail Exchange Record)**
Specifica quale è il server responsabile della gestione e-mail per un determinato dominio, quel server ci servirà per inviare mail. Per esempio:

```
miosito.com    MX    10 mail.miosito.com
```

Nell'esempio noti quel numero 10, cosa è? la priorità del server scelto per inviare mail; può capitare ci siano più server utilizzati per inviare mail, i numeri più bassi hanno priorità maggiore.

###### **TXT Record (Text Record)**
Contiene informazioni di testo, usate per configurazioni di sicurezza o verifiche. Per esempio:

```
miosito.com    TXT    "v=spf1 include:_spf.google.com ~all"
```

Viene utilizzato per [[Autenticazione delle mail (SPF, DKIM e DMARC)]].
##### **NS Record (Name Server Record)**
Indica quali sono i server DNS autorevoli per un determinato dominio, questi server contengono i record DNS per quel dominio. Per esempio:

```
miosito.com    NS    ns1.providerdns.com
```

##### **Come si gestiscono i record DNS?**
Tramite dei pannelli di configurazione, sono consultabili:

- **Dal pannello che ti è stato fornito dal tuo registrar:** pannelli interni ad aree cliente Aruba, GoDaddy, Google Domains o simili.
  
- **Pannelli di servizi DNS esterni:** come Cloudflare, AWS Route 53 o Google Cloud DNS (di questo non ne sei sicuro, e non hai mai visto un esempio; cerca per confermare).
***
