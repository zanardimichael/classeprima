---
title: Rappresentazione audio e video
description: La rappresentazione digitale di audio e video
---

# La rappresentazione digitale di audio e video

Oltre ai testi e alle immagini statiche, i calcolatori gestiscono segnali multimediali che evolvono nel tempo, come suoni e filmati. Per essere elaborati, questi segnali analogici devono essere convertiti in formato digitale.

## 1. L'audio digitale

Da un punto di vista fisico, il suono è una variazione della pressione dell'aria nel tempo. Si tratta di un **segnale analogico**, ovvero continuo (assume un valore per ogni istante di tempo). Per rappresentare questo segnale dentro un computer, che lavora in modo discreto (con valori finiti, cioè solo per alcuni istanti di tempo), è necessario un processo di trasformazione che coinvolge una scheda di acquisizione audio e che viene chiamato **digitalizzazione**.

La digitalizzazione avviene tramite il **campionamento**: il sistema misura e registra il valore dell'onda sonora a intervalli di tempo regolari. Se questi intervalli sono sufficientemente ravvicinati, è possibile ricostruire il suono originale in modo fedele.

### Teorema di Nyquist-Shannon: quanti campioni servono?

C'è una domanda fondamentale nel processo di digitalizzazione: "ogni quanto devo misurare l'onda sonora per essere sicuro di poterla ricostruire fedelmente?". Se preleviamo pochi campioni, il suono risulterà distorto; se ne preleviamo troppi, sprecheremo memoria inutilmente. La regola d'oro è dettata dal **teorema di Nyquist-Shannon**. In parole semplici, si afferma che la frequenza di campionamento deve essere almeno il doppio della frequenza massima del suono che vogliamo registrare.

Se il campionamento è troppo lento, il computer non riesce a "stare dietro" alle vibrazioni veloci dell'onda sonora e finisce per interpretarle erroneamente come suoni distorti (fenomeno detto **aliasing**).

L'orecchio umano può percepire frequenze fino a un massimo di circa 20'000 Hz (20 KHz). Applicando il teorema, per registrare musica ad alta fedeltà serve una frequenza di oltre 40'000 Hz.

### I formati dei file audio

I file audio si classificano in tre categorie principali in base alla compressione:

*   **File audio non compressi:** occupano molto spazio perché mantengono intatta la conversione da analogico a digitale. Un esempio è il formato **.pcm** (pulse code modulation), usato nei CD e DVD.
*   **File compressi senza perdita (lossless):** riducono le dimensioni del file senza eliminare informazioni, permettendo una ricostruzione perfetta dell'originale. Un esempio è il formato **.aac**, che risparmia circa metà dello spazio, ma è usato raramente.
*   **File compressi con perdita (lossy):** sono i più diffusi. Riducono drasticamente le dimensioni eliminando i suoni che l'orecchio umano fatica a percepire. Il formato più noto è l' **.mp3**, compatibile con quasi tutti i dispositivi (smartphone, smart TV, ecc.).

## 2. Il video digitale

Un video è essenzialmente una sequenza di immagini statiche, chiamate **fotogrammi** (o frames), riprodotte velocemente per creare l'illusione del movimento. La fluidità dipende dal **frame rate**, cioè il numero di fotogrammi al secondo:

*   Standard PAL (vecchia TV): 25 fotogrammi al secondo.
*   Sistema UHD (ultra high definition): prevede fino a 120 fotogrammi al secondo.

Altri fattori che influenzano la qualità e il peso del file sono la profondità del colore, la risoluzione e l'audio associato.

### Formati contenitore e codec

È fondamentale distinguere tra il "contenitore" e il metodo di compressione. Il **formato contenitore** è un file che racchiude al suo interno la traccia video, l'audio e i metadati (informazioni descrittive come i sottotitoli). I più noti sono:

*   **.mp4:** ottimo compromesso tra compressione e qualità, molto diffuso sul web.
*   **.avi:** formato storico, molto compatibile ma ormai obsoleto (gestisce una sola traccia audio).
*   **.mkv:** alta qualità, supporta menu e tracce multiple, ma genera file di grandi dimensioni.

Per leggere e salvare questi file serve un software chiamato **codec** (codificatore-decodificatore). Ogni formato usa specifici codec, che nel sistema Windows sono spesso file con estensione .dll (es. MPEG-4 e Xvid).

## 3. Dimensioni, risoluzione e streaming

### La risoluzione

La dimensione di un video si esprime in pixel (larghezza \* altezza) o indicando solo l'altezza seguita dalla lettera "p". Il rapporto tra le due dimensioni è detto **aspect ratio** (es. 16:9 per il widescreen).

Ecco le risoluzioni principali (osservando la quantità di megapixel per frame):

*   **4K (2160p):** $3840 \times 2160$ pixel (circa 8.3 MP).
*   **1600p:** $2560 \times 1600$ pixel (4.1 MP).
*   **1080p (Full HD):** $1920 \times 1080$ pixel (2.1 MP).
*   **720p (HD):** $1280 \times 720$ pixel (0.9 MP).

### Lo streaming e il bitrate

Per fruire dei video in rete senza scaricarli completamente si usa il **live streaming**. Questo richiede una connessione stabile (fibra o ADSL veloce). Un parametro chiave è il **bitrate**, misurato in Mbps (megabit al secondo). Esso determina la qualità del video e la velocità di dati necessaria: per una buona visione, il bitrate varia tipicamente tra 2,5 e 5 Mbps a seconda del tipo di video.