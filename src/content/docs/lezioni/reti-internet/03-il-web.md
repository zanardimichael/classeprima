---
title: Il Web
description: Navigare nel Web - DNS, HTTP e HTTPS
---

## Navigare nel Web: DNS, HTTP e HTTPS

### Il DNS (Domain Name System)
Il DNS è spesso definito l'elenco telefonico di Internet. Gli esseri umani ricordano facilmente i nomi (es. google.it), ma i computer comunicano solo tramite indirizzi IP (es. 142.250.184.67).
- **Funzionamento**: Quando digiti un URL nel browser, il computer interroga un Server DNS chiedendo: "Qual è l'indirizzo IP associato a questo nome?".
- **Risoluzione**: Il DNS risponde con l'IP corretto e il browser può finalmente contattare il server che ospita il sito.

### Il Protocollo HTTP (HyperText Transfer Protocol)
L'HTTP è il linguaggio che usano il browser (client) e il server per scambiarsi informazioni.
- **Richiesta/Risposta**: Il browser invia una Request (es. "Inviami la pagina index.html") e il server risponde con un Response (il contenuto della pagina).
- **Limiti**: I dati inviati tramite HTTP sono in chiaro. Se qualcuno "intercettasse" la connessione (un attacco chiamato Man-in-the-Middle), potrebbe leggere tutto ciò che scrivi, comprese password o numeri di carta di credito.

### Il Protocollo HTTPS (HTTP Secure)
L'HTTPS è la versione sicura dell'HTTP. Utilizza un protocollo di crittografia chiamato TLS (Transport Layer Security).
- **Crittografia**: I dati vengono "rimescolati" prima di essere inviati. Solo il destinatario ha la chiave per decifrarli.
- **Autenticazione**: Grazie ai Certificati Digitali, l'HTTPS garantisce che il sito a cui sei collegato sia davvero quello che dichiara di essere (e non un sito clone creato da un hacker).
- **Identificazione visiva**: I browser segnalano la sicurezza con l'icona di un lucchetto accanto all'indirizzo.

### Esempio pratico: Il viaggio di una richiesta
1. Utente: Digita www.wikipedia.org.
2. DNS: Traduce www.wikipedia.org in 103.102.166.224.
3. HTTPS: Stabilisce una connessione sicura e criptata con quell'IP e invia la pagina al nostro PC.
4. Browser: Visualizza la pagina di Wikipedia.

:::danger[Attenzione!]
Se un sito web vi chiede dati personali ma l'indirizzo inizia con http:// (senza la "S"), non inserite mai i vostri dati! È come gridare la propria password in una piazza affollata.
:::

<div style="text-align: center;">

| Caratteristica  | HTTP                      | HTTPS                              |
|-----------------|---------------------------|------------------------------------|
| Porta standard  | 80                        | 443                                |
| Sicurezza       | Bassa (dati in chiaro)    | Alta (dati crittografati)          |
| Certificato     | Non richiesto             | Richiesto (Certificato SSL/TLS)    |
| Utilizzo ideale | Siti informativi pubblici | "Login, pagamenti, social network" |

</div>

## Il Modello Client-Server
In informatica, la comunicazione in rete non avviene tra "pari", ma segue solitamente una gerarchia composta da due ruoli distinti: il Client e il Server.

### Chi sono i protagonisti?
- **Il Client (Il Cliente)**: È il dispositivo o il software che richiede un servizio o una risorsa.
  - *Esempi*: Il tuo smartphone, il tuo PC, il browser (Chrome/Safari), l'app di Instagram.
- **Il Server (Il Servitore)**: È un computer potente, sempre acceso e connesso a Internet, che risponde alle richieste fornendo i dati necessari.
  - *Esempi*: I computer di Google che ospitano i video di YouTube, i server di posta elettronica, i server dei videogiochi online.

### Il Ciclo della Comunicazione (Request-Response)
La comunicazione tra Client e Server avviene sempre in due fasi principali:
- Richiesta (Request): Il Client invia un messaggio al Server chiedendo qualcosa (es. "Voglio vedere la pagina www.wikipedia.org").
- Risposta (Response): Il Server elabora la richiesta, cerca i dati e li spedisce indietro al Client (es. invia il testo e le immagini della pagina).