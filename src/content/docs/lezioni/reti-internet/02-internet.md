---
title: Internet
description: Le tecnologie di collegamento della rete globale
---

## Gli ISP: Internet Service Provider

### Definizione

Un Internet Service Provider (ISP), in italiano "Fornitore di Servizi Internet", è un'organizzazione o un'azienda che offre agli utenti (privati o aziende), solitamente dietro pagamento di un abbonamento, l'accesso a Internet e ai servizi correlati.

### Funzioni Principali

L'ISP funge da intermediario tra il dispositivo dell'utente e la "spina dorsale" (backbone) di Internet. Le sue funzioni includono:
- Connettività: Fornire il collegamento fisico e logico alla rete globale.
- Routing: Instradare il traffico dati dell'utente verso la destinazione corretta.
- Assegnazione Indirizzi IP: Fornire un indirizzo IP (statico o dinamico) necessario per navigare.
- Servizi Accessori: Hosting di siti web, registrazione di domini e caselle di posta elettronica (E-mail).

## Tecnologia FTTx

Con FTTx si intendono le varie architetture di collegamento internet fibra misto rame, di seguito la lista delle varie tecnologie con relativi esempi di implementazione:

- **FTTH** - *Fiber-to-the-home* (letteralmente "fibra fino a casa"): il collegamento in fibra ottica raggiunge la singola unità abitativa, per esempio una scatola sul muro di una casa. È la soluzione più costosa, ma anche l'investimento a più lungo termine che garantisce la massima velocità di trasmissione fino all'utente finale in previsione di servizi di rete più evoluti.
- **FTTB** - *Fiber-to-the-building* o *Fiber-to-the-basement* (letteralmente "fibra fino all'edificio" o "fibra fino alle fondamenta"): il collegamento in fibra ottica raggiunge il limite del palazzo o alla schiera, per esempio sino allo scantinato o ai garage per una o più unità abitative (appartamenti o villette), mentre il collegamento finale con l'appartamento rimane su filo di rame oppure con cablaggio in fibre ottiche polimeriche e tecnologia ethernet.
- **FTTC** o **FTTS** - *Fiber-to-the-cabinet* o *Fiber-to-the-curb* o *Fiber-to-the-street* (letteralmente "fibra fino all'armadio" o "fibra fino al cordolo del marciapiede"): il collegamento (molto simile al **FTTN**) arriva in una cabina esterna molto vicina alla sede dell'utente o al successivo armadio distributore, tipicamente entro 300 metri.
- **FTTN** - *Fiber-to-the-node* o anche *Fiber-to-the-exchange* (**FTTE**) (letteralmente "fibra fino al nodo" o "fibra fino allo scambio"): il collegamento in fibra ottica arriva in una cabina esterna distante diversi chilometri dalla sede del cliente, cioè tipicamente fino allo stadio di linea della rete telefonica, mentre il collegamento finale rimane su filo di rame.
- **FTTW** o **FTTR** - Fiber-to-the wireless o Fiber-to-the-radio (letteralmente "fibra fino alla base radio"): la fibra arriva fino a un ponte radio detto anche BTS e viene ricevuta da un'antenna posta sul tetto dell'edificio; questa tecnologia viene spesso usata per portare la fibra ottica dove non è possibile arrivare con il cavo.

<p style="text-align: center;">
    <img src="/internet/FTTX.svg" style="display: inline-block" alt="FTTx">
</p>

<div style="text-align: center;">

| Tecnologia | Distanza della fibra dal router              | Velocità massima   |
|------------|----------------------------------------------|--------------------|
| FTTH       | 0m, il collegamento arriva diretto al router | Fino a 10 Gbps     |
| FTTB       | Distanza dal router al seminterrato          | Fino a 1 Gbps      |
| FTTC       | Fino a 300m                                  | Fino a 300 Mbps    |
| FTTN       | Dai 300m                                     | Dai 25 ai 100 Mbps |
| FTTW       | Fino a 15km                                  | Fino a 1 Gbps      |

</div>

:::note[Lo sapevi che?]
Quando ti colleghi al Wi-Fi di casa, il tuo router comunica con l'ISP attraverso un protocollo chiamato PPPoE (Point-to-Point Protocol over Ethernet) per autenticare il tuo abbonamento e permetterti di navigare.
:::

## Indirizzi di Rete: IP vs MAC
Per permettere ai dati di viaggiare correttamente nel web, ogni dispositivo ha bisogno di identificatori univoci. Possiamo paragonarli al sistema postale: uno è il nome del destinatario, l'altro è l'indirizzo della casa. 

### Indirizzo MAC (Media Access Control)
L'indirizzo MAC è l'indirizzo fisico (o hardware) assegnato univocamente dal produttore alla scheda di rete (NIC).
- Caratteristiche: È permanente e "scritto" nell'hardware. Non cambia mai, ovunque si trovi il dispositivo.
- Formato: Composto da 48 bit, solitamente scritto come 6 coppie di cifre esadecimali (es: 00:1A:2B:3C:4D:5E).
- Livello ISO/OSI: Opera al Livello 2 (Data Link).
- Scopo: Identificare un dispositivo specifico all'interno di una rete locale (LAN).

### Indirizzo IP (Internet Protocol)
L'indirizzo IP è l'indirizzo logico assegnato a un dispositivo quando si connette a una rete.
- Caratteristiche: È dinamico (può variare). Dipende dalla rete a cui sei connesso (es. l'IP di casa è diverso da quello della scuola).
- Versioni principali:
  - IPv4: Formato da 32 bit, scritto come 4 numeri decimali, blocco va da 0 a 255 (es: 192.168.1.15).
  - IPv6: Creato per ovviare alla scarsità di indirizzi IPv4, usa 128 bit (es: 2001:0db8:85a3...).
- Livello ISO/OSI: Opera al Livello 3 (Network).
- Scopo: Permettere l'instradamento dei dati tra reti diverse in tutto il mondo.

:::note[Nota bene]
I livelli ISO/OSI verranno trattati in dettaglio in quarta nella materia Sistemi e Reti
:::