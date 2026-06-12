---
title: Analogico e digitale
description: Le differenze tra analogico e digitale
---
## 1. Introduzione ai Segnali

Nel campo dell’informatica, delle telecomunicazioni e dei sistemi elettronici, un **segnale** è una grandezza fisica variabile nel tempo alla quale è associata un’informazione. Esistono due modi fondamentali per rappresentare ed elaborare questa informazione: la forma analogica e la forma digitale.

### 1.1 Il Segnale Analogico

Un segnale si definisce **analogico** quando la grandezza fisica che lo rappresenta varia nel tempo in modo **continuo**, sia nel dominio del tempo che in quello dei valori (ampiezza). Ciò significa che, presi due istanti di tempo vicini a piacere, il segnale assumerà infiniti valori intermedi.

Esempi fisici:

* La voce umana trasmessa attraverso la pressione dell’aria.
* La temperatura ambientale registrata durante una giornata.
* La tensione elettrica ai capi di un microfono.

L’aggettivo ”analogico” deriva da analogia: l’andamento della grandezza elettrica (es. la tensione) segue in modo perfettamente analogo l’andamento della grandezza fisica reale (es. l’intensità del suono).

### 1.2 Il Segnale Digitale
Un segnale si definisce **digitale** (dall’inglese digit, cifra) quando le grandezze sono rappresentate in modo **discreto**. Un segnale digitale non varia in modo continuo, ma può assumere solo un insieme finito di valori ben definiti in corrispondenza di determinati istanti di tempo. Nel contesto informatico, questi valori sono rappresentati mediante cifre binarie (bit: 0 e 1).

### 1.3 Vantaggi del Digitale rispetto all’Analogico

L’elettronica moderna e le reti di calcolatori si basano quasi esclusivamente sul digitale per una
serie di motivi strategici:

1. **Immunità al rumore**: I segnali analogici tendono a degradarsi e ad accumulare disturbi (rumore) durante la trasmissione. Nei segnali digitali, poiché contano solo le soglie logiche (es. presenza o assenza di tensione), è molto più facile distinguere lo 0 dall’1 anche in presenza di forti disturbi.
2. **Facilità di memorizzazione ed elaborazione**: I bit possono essere facilmente scritti su memorie RAM, Hard Disk o Flash, e processati dalle CPU e dai DSP (Digital Signal Processor).
3. **Riproducibilità**: Una copia di un file digitale è identica all’originale, senza alcuna perdita di qualità (a differenza di quanto accadeva con le vecchie cassette a nastro analogiche).

## 2. Il Processo di Conversione Analogico-Digitale (ADC)

Poiché il mondo reale è intrinsecamente analogico ma i computer elaborano solo bit, è necessario un dispositivo mediatore: 
il **Convertitore Analogico-Digitale** (ADC - Analog to Digital Converter).

Il processo di conversione si articola in tre fasi sequenziali fondamentali:

![Processo](/analogico-digitale/processo.png)

### 2.1 Campionamento (Sampling)

Il campionamento consiste nel "leggere" il valore del segnale analogico a intervalli di tempo regolari e costanti. 
Il tempo che intercorre tra due letture successive si chiama **Periodo di Campionamento** ($T_s$).

Il numero di campioni prelevati in un secondo prende il nome di **Frequenza di Campionamento** ($f_s$), ed è legata al periodo dalla relazione:

$f_s = \frac{1}{T_s} \quad [\text{misurata in Hertz, Hz}]$

**Il fenomeno dell’Aliasing**: Se non si rispetta questa condizione ($f_s < 2 \cdot f_{max}$), le frequenze più alte si ”ribaltano” sovrapponendosi a quelle basse. 
Questo genera una distorsione grave chiamata **aliasing**. Un esempio visivo comune è l’effetto per cui le ruote delle auto nei film sembrano girare all’indietro (la frequenza di cattura della telecamera è troppo bassa rispetto alla rotazione della ruota). 
Nelle schede audio, per evitare l’aliasing, si posiziona sempre un **filtro anti-aliasing** (un filtro passa-basso) prima del campionatore.

**Applicazione pratica**: L’orecchio umano percepisce suoni fino a circa 20 kHz. Per il teorema di Nyquist, la frequenza di campionamento minima per l’audio ad alta fedeltà deve essere di 40 kHz. Lo standard del CD Audio utilizza infatti 44.1 kHz.

:::note[Cos'è un filtro passa-basso?]
Un filtro passa basso è un sistema che permette il passaggio di frequenze al di sotto di una data soglia, detta frequenza di taglio, eliminando le alte frequenze.
:::

### 2.1.1 Il Teorema di Nyquist-Shannon
Quanto spesso dobbiamo campionare un segnale per essere sicuri di non perdere informazioni?

La risposta è fornita dal Teorema di Nyquist-Shannon:

>Per poter ricostruire fedelmente un segnale analogico a partire dai suoi campioni,
la frequenza di campionamento $f_s$ deve essere almeno pari al doppio della frequenza
massima ($f_{max}$) contenuta nello spettro del segnale di partenza

### 2.2 Quantizzazione (Quantization)
Mentre il campionamento rende discreto il tempo, il segnale ha ancora un’ampiezza continua (il valore del campione può essere un numero con infiniti decimali). 
La **quantizzazione** si occupa di discretizzare l’ampiezza del segnale.

Il range totale del convertitore viene diviso in un numero finito di livelli ($L$). 
Ogni campione viene approssimato al livello di quantizzazione più vicino. 
Il numero di livelli disponibili dipende strettamente dal numero di bit ($N$) utilizzati dal convertitore hardware:

$f_s \ge 2 \cdot f_{max}$

Se usiamo un convertitore a 3 bit, avremo $2^3$ = 8 livelli di ampiezza. Se usiamo un convertitore moderno a 16 bit (come nei CD), avremo $2^{16}$ = 65.536 livelli, garantendo un’approssimazione incredibilmente più precisa.

### 2.2.1 Errore e Rumore di Quantizzazione
Poiché arrotondiamo il valore reale del segnale al livello più vicino, introduciamo inevitabilmente un piccolo errore, chiamato **errore di quantizzazione** ($ϵ$). 
Questo errore si manifesta sotto forma di un disturbo di sottofondo noto come **rumore di quantizzazione**. Più bit utilizziamo ($N$ elevato), più i livelli sono vicini, minore sarà l’errore commesso e maggiore sarà il rapporto segnale/rumore (SNR).

### 2.3 Rappresentazione Grafica di Campionamento e Quantizzazione
Il grafico seguente mostra un segnale analogico continuo (in linea tratteggiata) che viene campionato a intervalli regolari lungo l’asse t e quantizzato su 8 livelli (3 bit) lungo l’asse delle
ampiezze.

![Campionamento](/analogico-digitale/campionamento.png)

### 2.4 Codifica (Encoding)

L’ultima fase consiste nel trasformare il valore numerico assegnato a ciascun livello quantizzato in una stringa di bit. Come si nota nel grafico precedente, a ciascuno degli 8 livelli corrisponde un codice binario univoco da 000 a 111.

Se il nostro segnale campionato nell’istante t = 1.0 viene quantizzato al livello 3.5 V, la fase di codifica emetterà in output la sequenza binaria 110. La sequenza finale di bit trasmessa o memorizzata sar`a semplicemente la concatenazione dei codici di ciascun campione.

## 3. Il Processo Inverso: Ricostruzione del Segnale (DAC)

Quando ascoltiamo un file MP3 o un video su YouTube, i bit memorizzati devono essere riconvertiti in onde sonore analogiche per le nostre cuffie. Questo compito spetta al **Convertitore Digitale-Analogico** (DAC - Digital to Analog Converter).

Il DAC riceve i bit, rigenera i livelli di tensione corrispondenti ai campioni e genera un segnale ”a gradini” (chiamato mantenimento di ordine zero). Questo segnale non è ancora perfettamente liscio come l’originale. Per eliminare le discontinuità dei gradini e ricostruire la curva analogica pulita, il segnale viene fatto passare attraverso un **filtro di ricostruzione** (un filtro passa-basso analogico)