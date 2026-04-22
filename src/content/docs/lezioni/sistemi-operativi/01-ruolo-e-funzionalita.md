---
title: Ruolo e funzionalità
description: Il ruolo dei sistemi operativi e le loro funzionalità
---

# Il ruolo dei sistemi operativi e le loro funzionalità

Il sistema operativo (S.O.) appartiene alla categoria del software di base e ricopre il ruolo fondamentale di gestore delle risorse hardware, come la memoria, le periferiche e la CPU. Il suo scopo principale è fornire un modo semplice all'utente di impartire comandi alla macchina, permettendo così di dialogare con il computer senza dover possedere conoscenze tecniche approfondite sull'hardware utilizzato.

In questo contesto, le "**risorse**" sono tutti quegli elementi hardware o software utilizzati da un programma per eseguire il proprio compito (es. il monitor, la stampante, ma anche la memoria per salvare i progressi di un videogioco).

Fino agli anni '70, l'utente era obbligato a fornire comandi mediante interfaccia testuale, **CLI** (Command-Line Interface), di difficile uso. A causa della crescente popolarità dei Personal Computer, per l'utente non esperto venne sviluppata anche un'interfaccia grafica di uso immediato e intuitivo, **GUI** (Graphical User Interface), composta di una scrivania virtuale e di cartelle in cui trascinare e organizzare i singoli file, ciò grazie al dispositivo di puntamento detto mouse.

## L'architettura "a buccia di cipolla" (onion skin)

Il sistema operativo non è un singolo blocco, ma è formato da un insieme di programmi organizzati in modo che ciascuno si occupi di un compito specifico. Si tratta di un insieme di diversi software organizzati a cipolla. Questa struttura è definita **onion skin**: i programmi posizionati nei livelli più interni (vicino al nucleo) interagiscono maggiormente con l'hardware, mentre i programmi collocati più all'esterno comunicano direttamente con l'utente tramite l'interfaccia.

La struttura è gerarchica: ogni strato si serve esclusivamente dello strato inferiore. Questa netta separazione è di vitale importanza anche per la sicurezza: alcune operazioni critiche possono essere eseguite solo dal sistema operativo e non dagli altri programmi applicativi.

### 1° livello: il nucleo (kernel)

Il nucleo, o **kernel**, è il cuore del sistema e gestisce direttamente la CPU, organizzando l'esecuzione dei programmi. Il kernel compie un'operazione fondamentale: associa un "**processo**" a ogni programma in esecuzione. C'è una differenza sostanziale tra questi due concetti: un programma è un'entità statica (la semplice descrizione delle azioni da compiere), mentre il processo è un'entità dinamica (l'insieme delle azioni che vengono effettivamente compiute dal processore in fase di esecuzione).

Nei moderni sistemi "multiprogrammati", capaci di gestire più software contemporaneamente, il kernel definisce l'esecuzione alternata dei processi, facendo in modo che la CPU passi rapidamente dall'uno all'altro per portarli tutti a termine in modo fluido (e dando, così, una parvenza di parallelismo all'utente: si possono fare più cose contemporaneamente, come prendere appunti su Word e riprodurre un video su YouTube).

### 2° livello: il gestore della memoria centrale

Per avere processi in esecuzione, devo avere memoria a disposizione. Per poter funzionare, tutti i programmi devono essere caricati nella memoria **RAM**. Tuttavia, la RAM ha una dimensione fisica limitata e non può contenere tutti i programmi attivi simultaneamente.

Il sistema operativo gestisce questa limitazione frazionando la memoria e i programmi in sezioni specifiche (chiamate pagine e segmenti). Il gestore si occupa di caricare le pagine necessarie ed effettuare lo scaricamento di quelle non più utilizzate man mano che l'esecuzione avanza.

Inoltre, il S.O. garantisce ai programmi un'enorme quantità di "**memoria virtuale**". Sfruttando uno spazio dedicato sul disco fisso (chiamato file di paging), il sistema simula di avere a disposizione molta più memoria RAM di quella fisica installata. Le operazioni continue di spostamento di queste pagine di dati dalla memoria di massa alla RAM prendono il nome di **swapping**.

### 3° livello: il gestore delle periferiche

Le periferiche sono tutti i componenti hardware del calcolatore, sia interni sia connessi esternamente tramite porte (es. USB e HDMI) come mouse, tastiera, monitor, stampanti e masterizzatori. Durante la loro esecuzione, i processi fanno continue richieste di periferiche di input/output e il S.O. deve regolare e concorrere a questo accesso assegnando le risorse.

Se più processi richiedono la stessa risorsa unica contemporaneamente (es. la stampante), il S.O. si incarica di gestire l'accesso alternato ed eventuali code di attesa. Un esempio pratico applicato alle stampanti è lo **spooling**: gli output generati dai processi non vanno direttamente alla stampante occupata, ma vengono salvati temporaneamente sul disco rigido (in file di spool) e messi in coda per essere stampati uno alla volta dal sistema operativo.

### 4° livello: il file system

Il **file system** provvede alla gestione di tutto ciò che deve essere archiviato in modo permanente sulle memorie di massa. Ogni elemento registrato prende il nome di file. Il file system rende la vita semplice all'utente e ai programmatori permettendo di usare nomi simbolici e di organizzare i dati in cartelle (directory) all'interno di strutture gerarchiche. Si usa spesso la metafora dell'albero, poiché cartelle e file possono essere visti come rami e foglie che nascono da un unico punto detto radice.

Un file system efficiente deve gestire in modo ottimale lo spazio sul disco e garantire accessi veloci ai dati, fornendo allo stesso tempo meccanismi di protezione (contro interventi dannosi o non autorizzati) e mettendo a disposizione operazioni di base come copia, cancellazione e rinomina.

Il file system stabilisce anche che ogni file sia individuato da un pathname univoco; **pathname = percorso di cartelle da attraversare per arrivare al file + nome file + estensione file**. Non possono quindi esistere due file con uguale pathname.

Fisicamente, un disco rigido è suddiviso in tracce e settori che formano i cluster, ovvero la quantità minima di spazio allocabile sul disco per contenere un file. Un file può occupare svariati blocchi (cluster), anche non contigui tra loro; è compito esclusivo del file system gestire e mantenere aggiornata una tabella che traccia quali blocchi sono attualmente occupati e quali sono liberi per nuove registrazioni.

### 5° livello: l'interfaccia con l'utente

L'interfaccia, o **shell**, è lo strato che si frappone tra la macchina e l'utente, consentendo il dialogo effettivo. Esistono due grandi tipologie di interfacce: quelle che funzionano a linea di comando inserendo testo (**CLI**), e quelle tipiche dei sistemi operativi moderni user-friendly che usano finestre e icone (**GUI**).

### 6° livello: programmi applicativi

È lo strato più esterno, quello composto dai vari software (es. word processor, browser, giochi) utilizzati direttamente dall'utente per compiere le proprie attività.

## Dove si trova il sistema operativo e l'avvio del PC

Quando il computer è spento, il sistema operativo risiede in modo permanente sul disco rigido o su un disco a stato solido (memoria di massa). Per poter essere utilizzato, al momento dell'accensione il S.O. deve essere prima trasferito nella memoria RAM. Questa fase cruciale prende il nome di **bootstrap**.

Il processo di bootstrap segue una precisa fase diagnostica e di avvio:

*   **Accensione**: si fornisce corrente al sistema.
*   **POST (Power-On Self Test)**: avviene una diagnostica iniziale dell'hardware essenziale, operazione eseguita direttamente dal **firmware** della macchina (il **BIOS**).
*   **Controllo periferiche**: vengono esaminati l'hard disk e i dispositivi plug & play.
*   **Avvio del boot loader**: il sistema va a cercare un record speciale (chiamato **MBR**) sul disco rigido, che contiene le istruzioni per iniziare il caricamento effettivo.
*   **Avvio del sistema operativo**: i moduli essenziali del kernel vengono copiati nella RAM e il SO prende il controllo della macchina.

Spesso, l'ultima fase visibile del bootstrap si conclude con l'identificazione dell'utente tramite la procedura di **login**. Qui è richiesto l'inserimento di un nome utente e di una password per ottenere l'accesso alle varie funzioni protette del sistema operativo.