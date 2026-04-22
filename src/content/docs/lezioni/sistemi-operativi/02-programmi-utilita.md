---
title: I programmi di utilità
---

I programmi di utilità, o utilities, sono software che permettono di rendere più efficiente l'utilizzo del computer. Questi programmi possono essere forniti a corredo del sistema operativo stesso oppure possono essere resi disponibili da sviluppatori di terze parti; in quest'ultimo caso devono essere acquistati e installati separatamente. Di seguito vengono esaminate le principali categorie di programmi di utilità.

## 1. Le utilità di backup e pianificazione

Le utilità di backup rivestono un ruolo cruciale nella gestione di un sistema informatico. La loro funzione principale è quella di creare su supporti magnetici o ottici delle copie di salvataggio dei dati (e a volte anche delle applicazioni) presenti sul computer. È opportuno eseguire periodicamente queste operazioni per mettersi al riparo da malfunzionamenti dell'hard disk, errori di partizionamento, problemi del sistema operativo o attacchi di virus che potrebbero rendere inaccessibili i dati. L'operazione inversa, detta di *restore*, permette di ripristinare i dati danneggiati o persi a partire dall'ultima copia di backup salvata.

I metodi di backup più diffusi includono:

*   **Salvataggio su hard disk o SSD esterno**: è il metodo più tradizionale. Esistono due tecniche principali: il metodo incrementale (che salva solo le modifiche avvenute rispetto al backup immediatamente precedente) e il metodo differenziale (che salva le differenze rispetto al primissimo backup completo).
*   **Backup online (remoto)**: sfrutta la connessione Internet. Inizialmente si usavano i servizi di posta elettronica, ma per ovviare a limiti di spazio e sicurezza, oggi si usano servizi di backup remoto su server dedicati, che permettono anche il salvataggio di interi sistemi.
*   **Compressione**: memorizzazione di file e dati in un unico archivio compresso, generalmente in formato .zip, salvato localmente.
*   **Clonazione**: crea una copia esatta, byte per byte, su un hard disk secondario identico al principale; in caso di guasto, il disco di backup può sostituire direttamente quello danneggiato.
*   **Imaging**: crea una copia esatta di una partizione o di un disco sotto forma di file immagine, che può essere salvato su un hard disk diverso anche di capacità differente.

Nei sistemi operativi come Windows 10, l'utilità di backup è integrata e accessibile dal menu Start sotto le voci "Impostazioni", "Aggiornamento e Sicurezza" e infine "Backup".

L'utilità di pianificazione: In Windows è integrata anche l'utilità di pianificazione, che permette di eseguire programmi in modo automatico. Questo evita all'utente di doversi ricordare di avviare manualmente operazioni periodiche, come il backup o la pulizia del disco, potendole programmare su base giornaliera, settimanale o mensile.

## 2. Le utilità di partizionamento

Gli hard disk e le unità SSD moderne offrono notevoli capacità di memorizzazione. Le utilità di partizionamento permettono di suddividere l'unità fisica in più partizioni logiche, che il sistema e l'utente visualizzano come unità separate. Creare due partizioni (ad esempio, una per il sistema operativo e i programmi, l'altra per i file personali) semplifica molto il controllo degli accessi e la gestione dei backup. L'operazione di partizionamento è delicata e andrebbe eseguita, previa esecuzione di un backup, al momento dell'installazione del sistema operativo.

## 3. Le utilità di deframmentazione

Sull'hard disk, i file sono memorizzati all'interno di unità di dimensione fissa chiamate cluster. Se un file è più grande di un singolo cluster, viene frammentato in più porzioni. Nel normale ciclo di vita del computer, le continue operazioni di salvataggio e cancellazione portano alla frammentazione: i cluster che compongono un singolo file finiscono per essere scritti in zone distanti del disco. Questo costringe le testine di lettura/scrittura a continui spostamenti fisici, aumentando i tempi di accesso e peggiorando le prestazioni. L'utilità di deframmentazione ricompatta lo spazio, spostando i file su cluster contigui.

*Nota bene*: questa operazione non si utilizza sulle unità a stato solido (SSD), poiché in queste memorie il tempo di accesso non dipende dalla posizione fisica dei dati. In Windows 10 l'apposita utilità si chiama "Deframmenta e ottimizza unità".

## 4. Le utilità di compressione dei file

Queste utilità servono a ridurre lo spazio occupato dai file nella memoria di massa, utilizzando specifici algoritmi. Gli algoritmi si dividono in due categorie:

*   **Algoritmi lossless (senza perdita di dati)**: mantengono intatta l'integrità del file. Dopo la decompressione, il file torna esattamente allo stato originale senza aver perso informazioni. È il caso del formato .zip, particolarmente adatto per file di testo o dati. In Windows 10, si può comprimere rapidamente selezionando un file e usando il menu contestuale "Invia a Cartella compressa".
*   **Algoritmi lossy (con perdita di dati)**: sono tecniche di compressione "distruttiva". Rimuovono definitivamente parti di informazione considerate non necessarie. Sono usati per file grafici, audio o video, dove l'occhio o l'orecchio umano non percepiscono la lieve perdita di qualità. Esempi sono i formati .jpeg (immagini), .mp3 (audio) e .mpeg (video). Per l'audio, la compressione può ridurre il file a un ventesimo della dimensione originale.

## 5. I programmi antimalware

I programmi antimalware (o antivirus) sono essenziali per proteggere il sistema informatico dalle infezioni che possono arrivare da supporti rimovibili, allegati email o navigazione web. Il termine *malware* (malicious software) indica qualsiasi programma creato per causare danni.

Le principali categorie di malware includono:

*   **Virus**: codice che si lega ad altri programmi eseguibili e si diffonde quando il file infetto viene aperto, causando danni come la cancellazione di file o la formattazione del disco.
*   **Worm (verme)**: si autoreplica senza bisogno di legarsi a file eseguibili. Sfrutta la rete (come la posta elettronica) per inviare copie di sé stesso ad altri indirizzi, rimanendo attivo in memoria finché non si spegne il computer.
*   **Spyware**: raccoglie di nascosto le abitudini di navigazione dell'utente per trarne profitto (es. tramite pubblicità mirata o furto di dati). Spesso altera anche la pagina iniziale del browser o i preferiti. A differenza di virus e worm, non si diffondono da soli, ma richiedono l'intervento inconsapevole dell'utente per essere installati.

### Funzionamento dell'antivirus

Un buon antivirus esegue scansioni in memoria centrale e sui supporti. Se rileva un'infezione, procede secondo tre alternative:

*   Eliminazione del virus dal file infetto (disinfezione).
*   Messa in quarantena: se non è disinfettabile, il file viene spostato in un'area sicura, in attesa di un aggiornamento capace di rimuovere il virus.
*   Cancellazione del file: eseguita come ultima risorsa.

Per operare, l'antivirus si affida a diversi moduli:

*   Il **motore**, che cerca il pattern o "firma" virale all'interno dei file.
*   Il **file delle firme**, l'archivio dei virus conosciuti.
*   Un **modulo residente in memoria**, che analizza tutto in tempo reale durante i caricamenti.
*   Il **modulo degli aggiornamenti** (Live Update), fondamentale per scaricare costantemente dalla rete le nuove firme virali.

In Windows 10 è incluso il sistema di protezione "Sicurezza di Windows" (Windows Defender), che fa analisi periodiche per rilevare sia virus sia spyware.

*(Nota bene: a volte gli antivirus generano "falsi positivi", bloccando file innocui perché una loro porzione di byte somiglia casualmente alla firma di un virus).*

## 6. Altre utilità di sistema

Esistono altri strumenti utili che semplificano il lavoro quotidiano:

*   **Utilità per il recupero dei file cancellati**: quando si elimina un file, questo finisce nel Cestino (un'area temporanea) da cui può essere ripristinato. Se si "svuota il cestino", il sistema in realtà non distrugge fisicamente i dati, ma contrassegna quello spazio di memoria come "libero". Apposite utilità specializzate sono in grado di recuperare questi file, purché i loro cluster non siano stati già sovrascritti da nuovi dati.
*   **Visualizzatori di file**: permettono di aprire in sola lettura vari tipi di documenti senza dover possedere il programma che li ha generati. Sono utili anche per ispezionare file "sospetti" in sicurezza, senza rischiare di innescare macro virali o worm.
*   **Cattura di schermate**: strumenti per registrare immagini dello schermo intero, di singole finestre o di selezioni specifiche, usati frequentemente per creare manuali e guide.
*   **Personalizzazione del desktop**: utility che consentono di cambiare disposizione delle icone, sfondi, salvaschermi e colori. Oltre a rendere l'ambiente più gradevole dal punto di vista estetico, favoriscono la razionalizzazione del lavoro permettendo di sistemare gli strumenti secondo i gusti e i bisogni dell'utente.