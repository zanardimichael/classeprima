---
title: Rappresentazione delle immagini
description: La rappresentazione delle immagini nel calcolatore
---

# La rappresentazione delle immagini nel calcolatore

Le tecniche per rappresentare le immagini all'interno di un computer si suddividono principalmente in due grandi categorie: la tecnica **bitmap** (o raster) e la tecnica **vettoriale**.

## 1. Tecnica bitmap

Si basa sulla suddivisione dell'immagine in una griglia di piccoli riquadri chiamati **pixel** (picture element). A ciascuno di questi elementi vengono associati uno o più valori numerici che ne definiscono il colore. Si può tranquillamente immaginare una sequenza di N bit (unico reale linguaggio del calcolatore a basso livello) associata a ogni pixel.

La qualità dell'immagine dipende da due fattori fondamentali:
*   La **dimensione**, ovvero il numero di pixel che compongono la griglia (orizzontale × verticale).
*   La **profondità di colore**, cioè la varietà di colori che ogni singolo pixel può assumere (dipendente dal numero N di bit associati a ogni pixel).

Sebbene il formato bitmap garantisca un'elevata portabilità (è riconosciuto da qualsiasi piattaforma), presenta due svantaggi principali: richiede una grande quantità di memoria e soffre del fenomeno del **blocking** (quando l'immagine viene ingrandita, i pixel diventano visibili e l'immagine risulta sfuocata o squadrata).

### Tipologie di immagini bitmap

#### Immagini in bianco e nero (1 bit)
Ogni pixel è rappresentato da N=1 bit:
*   se il bit vale 1: colore nero
*   se il bit vale 0: prevalenza di bianco.
    Questa rappresentazione è adatta solo per testi o disegni al tratto.

#### Immagini a sfumature di grigio (8 bit)
Le fotografie in bianco e nero vengono digitalizzate utilizzando 8 bit per pixel. Questo permette di codificare $2^8 = 256$ diverse sfumature di grigio.

#### Immagini a colori (RGB)
Le immagini a colori richiedono molte più informazioni. La tecnica impiegata è quella della **sintesi additiva**, basata sulla scomposizione di ogni colore nei tre fondamentali: rosso, verde e blu (RGB: Red Green Blue).
Il formato più diffuso prevede che ogni componente RGB sia rappresentata da 1 Byte (8 bit). Di conseguenza, ogni pixel richiede 24 bit totali (3 Byte). Il numero di colori rappresentabili è $2^{24}$ (più di 16 milioni di sfumature di colore!).

#### Tabella: Esempi di combinazioni di colori RGB (0-255)

| Colore    | R (Rosso) | G (Verde) | B (Blu) |
|:----------|:----------|:----------|:--------|
| Bianco    | 255       | 255       | 255     |
| Rosso     | 255       | 0         | 0       |
| Verde     | 0         | 255       | 0       |
| Blu       | 0         | 0         | 255     |
| Arancione | 255       | 165       | 0       |
| Giallo    | 255       | 255       | 0       |
| Marrone   | 150       | 75        | 0       |
| Viola     | 143       | 0         | 255     |
| Nero      | 0         | 0         | 0       |

**Nota:** Per la stampa su carta si utilizza un modello alternativo chiamato **CMYK** (Cyan, Magenta, Yellow, Black). A differenza dell'RGB (che somma luce), il CMYK usa la **sintesi sottrattiva**, creando i colori tramite l'assorbimento della luce da parte dei pigmenti.

### Formati di file e compressione

Poiché le immagini bitmap occupano molto spazio ("pesanti"), si utilizzano algoritmi di compressione per ridurne le dimensioni e velocizzare la trasmissione. La compressione mira a rappresentare le stesse informazioni del file originale occupando però meno spazio in memoria. A volte, per risparmiare spazio si abbassa la qualità dell'immagine, perdendo così informazioni in essa contenute.

Potete trovare file immagine con le seguenti estensioni:
*   **.bmp**: rappresentazione standard non compressa.
*   **.jpeg**: utilizza compressione **lossy** (con perdita di dati), poiché cala la qualità e compaiono artefatti visivi.
*   **.gif**: utilizza compressione **lossless** (senza perdita di dati), molto usato sul web per le dimensioni ridotte, ma permette un numero limitato di colori.
*   **.png**: utilizza compressione **lossless**, offrendo vantaggi rispetto al GIF, come la possibilità di codificare immagini usando 48 bit per pixel e di gestire le trasparenze.

## 2. Tecnica vettoriale

La tecnica vettoriale descrive le immagini non tramite pixel, ma attraverso **formule matematiche** che definiscono entità geometriche semplici (segmenti, rettangoli, cerchi). Ad esempio, un cerchio viene memorizzato specificando la posizione del centro e la lunghezza del raggio.

### Vantaggi principali
*   **Scalabilità infinita**: Un'immagine vettoriale può subire trasformazioni (ingrandimenti) senza alcuna perdita di qualità. È possibile ottenere la stessa definizione di stampa sia su un foglio A4 che su un cartellone pubblicitario.
*   **Modificabilità**: È facile modificare forme e colori o visualizzare solo i contorni (utile per guidare macchinari di taglio e incisione).
*   **Leggerezza**: Occupano generalmente meno spazio delle bitmap per immagini geometriche.

### Formati vettoriali comuni
*   **.eps** (Encapsulated PostScript): standard per l'elaborazione di immagini e disegni.
*   **.svg** (Scalable Vector Graphics): formato usato per il web, adattabile a qualsiasi pagina.
*   **.ai**: formato proprietario di Adobe Illustrator.

## 3. Calcolo dell'occupazione di memoria

Consideriamo un'immagine con dimensione $4096 \times 3072$ pixel (circa 12 Megapixel).

| Tipo di Immagine | Calcolo (Pixel \* Bit)           | Risultato (Bit)   | Risultato (Byte)  | Dimensione Approx. |
|:-----------------|:---------------------------------|:------------------|:------------------|:-------------------|
| Bianco e Nero    | $4096 \times 3072 \times 1$ bit  | $12'582'912$ bit  | $1'572'864$ Byte  | ~1,5 MB            |
| Scala di Grigi   | $4096 \times 3072 \times 8$ bit  | $100'663'296$ bit | $12'582'912$ Byte | ~12,5 MB           |
| Colori (RGB)     | $4096 \times 3072 \times 24$ bit | $301'989'888$ bit | $37'748'736$ Byte | ~37,7 MB           |

Questo esempio evidenzia perché l'uso di formati compressi (come JPEG o PNG) sia fondamentale per la gestione delle fotografie digitali a colori.