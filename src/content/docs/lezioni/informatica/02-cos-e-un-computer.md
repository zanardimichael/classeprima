---
title: Che cos'è un computer?
---

La parola **computer** deriva dal verbo latino *computare*, che significa letteralmente "contare" o "calcolare". Tuttavia, definire il computer come una semplice calcolatrice sarebbe riduttivo.
Mentre un elettrodomestico come la lavatrice è una macchina *special purpose* (cioè costruita per fare una sola cosa), il computer è una macchina **general purpose** (per uso generale): a seconda di come viene programmato, può svolgere compiti completamente diversi, dal permetterci di scrivere un testo, a farci navigare su Internet, fino a elaborare complessi calcoli scientifici.

Il suo scopo principale è elaborare enormi quantità di **dati** (elementi grezzi come numeri o testi) ad altissima velocità, per trasformarli in **informazioni** utili e organizzate.

Un computer è formato da due "anime" inseparabili: l'**Hardware** e il **Software**.
Per capire la differenza, immagina un pianoforte: il pianoforte fisico, con i suoi tasti e le sue corde, rappresenta l'hardware (la parte meccanica, elettronica e "dura" che si può letteralmente toccare); la musica che viene suonata, invisibile ma fondamentale, rappresenta il software (i programmi e i dati).

## L'Architettura di Von Neumann (Hardware)
Tutti i computer moderni, dai grandi server aziendali fino ai nostri smartphone, funzionano seguendo un modello teorico geniale inventato negli anni '40 dal matematico John von Neumann.

Prima di lui, i primissimi calcolatori elettronici (come l'ENIAC) non avevano una vera e propria memoria per i programmi: per far eseguire loro un calcolo diverso bisognava letteralmente staccare e riattaccare a mano centinaia di cavi elettrici.
L'idea rivoluzionaria di Von Neumann fu quella di utilizzare un'unica **Memoria Centrale** per memorizzare, sotto forma di numeri binari (0 e 1), **sia i dati grezzi da elaborare sia le istruzioni stesse dei programmi**.

Dal punto di vista logico, l'architettura di Von Neumann si basa su blocchi fondamentali che comunicano tra loro attraverso dei canali chiamati **Bus** (un insieme di conduttori su cui viaggiano i segnali elettrici):

### A. Il Processore (CPU - Central Processing Unit)
La CPU è il vero e proprio "cervello" del computer. È l'unità che elabora i dati, esegue i programmi e governa le altre componenti. Al suo interno troviamo:
*   La **ALU** (*Arithmetic Logic Unit*), che esegue i calcoli matematici e logici.
*   La **CU** (*Control Unit*), che coordina le attività dicendo al sistema "cosa fare" e in che ordine.
    La velocità della CPU è dettata da un orologio interno chiamato **clock**. La frequenza di clock si misura in **Hertz** (solitamente si parla di GHz, ovvero miliardi di cicli al secondo): più è alta la frequenza, più operazioni il computer compirà ogni secondo. Oggi i processori sono spesso *multicore*, cioè hanno più "cervelli" (core) che lavorano in parallelo spartendosi i compiti, riducendo consumi e surriscaldamento.

### B. La Memoria Centrale
La CPU, per lavorare velocemente, ha bisogno di avere i dati a portata di mano. Per questo usa la memoria centrale, divisa in due tipi:
*   **La RAM (Random Access Memory):** È la memoria di lavoro del computer. È velocissima, ma ha un difetto: è **volatile**. Questo significa che serve solo a contenere temporaneamente i dati e i programmi mentre li stiamo usando. Quando spegniamo il computer, tutto ciò che c'è nella RAM viene cancellato all'istante.
*   **La ROM (Read-Only Memory):** È una memoria molto più piccola, **non volatile** e di sola lettura. Contiene un programmino fondamentale (chiamato BIOS o firmware) che insegna al computer come accendersi e come far partire il sistema operativo.

### C. Le Memorie di Massa (Archiviazione)
Visto che la RAM si svuota spegnendo il PC, ci serve un posto dove salvare permanentemente i nostri documenti, i giochi e i programmi. Le memorie di massa sono il nostro "archivio" e non sono volatili. Le più importanti sono:
*   L'**Hard Disk (HDD):** Un disco magnetico tradizionale, molto capiente ma meccanico e un po' lento.
*   L'**SSD (Solid State Drive):** I dischi moderni a stato solido. Non avendo parti meccaniche in movimento, sono estremamente più veloci, silenziosi e resistenti, permettendo al computer di accendersi in pochissimi secondi.

### D. Le Periferiche (I sensi del computer)
Il computer deve comunicare con l'esterno per ricevere comandi dall'utente e mostrargli i risultati. A questo servono le unità periferiche:
*   **Periferiche di Input (ingresso):** Inseriscono dati *dentro* al computer. Esempi classici sono la tastiera, il mouse, il microfono, lo scanner e la webcam.
*   **Periferiche di Output (uscita):** Fanno uscire i risultati dell'elaborazione verso l'esterno. Gli esempi più comuni sono il monitor (o schermo), la stampante e gli altoparlanti (le casse).

:::note[Nota]
Alcuni dispositivi, come gli schermi **Touchscreen** dei tablet o degli smartphone, sono periferiche "miste" (sia input che output), perché mostrano le immagini e contemporaneamente ricevono i nostri comandi tramite il tocco.
:::

## Il Software (La mente)
Il **software** (dall'inglese *soft*, morbido) è la parte "logica" e intangibile del computer. Comprende tutti i dati, le informazioni e i programmi che dicono all'hardware cosa deve fare.
Senza il software, il computer più potente del mondo sarebbe solo un costoso fermacarte spento! Il software si divide in due grandi famiglie:
*   **I Sistemi Operativi:** I software "di base", assolutamente indispensabili, che gestiscono l'hardware e ci permettono di interagire con il PC. I più famosi sono Windows, macOS, Linux, e (sui dispositivi mobili) Android e iOS.
*   **I Programmi Applicativi (App):** Tutti quegli strumenti creati per compiti specifici dell'utente, come i browser per navigare su Internet (es. Google Chrome, Mozilla Firefox), i videogiochi, o programmi per scrivere come Word.