---
title: "Approfondimento: I componenti hardware di un computer"
---

Come abbiamo visto, l'hardware è l'insieme delle parti fisiche che compongono il PC. Questi pezzi lavorano tutti insieme e scegliere quelli giusti influisce enormemente sulle prestazioni generali della macchina. Vediamo i componenti fondamentali nel dettaglio:

## 1. La Scheda Madre (Motherboard)
La scheda madre è il vero e proprio "ponte" di connessione del computer: senza di essa i vari pezzi non potrebbero comunicare tra loro. Quando se ne sceglie una, bisogna considerare alcuni fattori critici:
*   **Il Chipset e la compatibilità con la CPU**. *(Nota: la compatibilità fisica è determinata dal **Socket**, ovvero il "sedile" o alloggiamento fisico sulla scheda madre in cui si incastra il processore. Ogni marca o generazione di processori richiede un socket specifico con una forma e dei contatti dedicati).*
*   Il numero di **slot per la RAM**, per capire quanta memoria si potrà installare in futuro.
*   La presenza di porte di connessione aggiornate (come USB, HDMI, DisplayPort) e il supporto per i velocissimi dischi **SSD NVMe**.

## 2. Il Processore (CPU - Central Processing Unit)
La CPU è il cuore e il "cervello" del PC, incaricato di eseguire calcoli e istruzioni. Nel mercato mondiale, i due **marchi principali** che producono CPU sono **Intel e AMD**.
La potenza e la velocità di un processore dipendono da caratteristiche ben precise:
*   **Frequenza di clock:** si misura in **GHz** e indica la velocità pura di esecuzione.
*   **Numero di core e thread:** i *core* sono dei "sotto-cervelli" interni. Più core ci sono, più attività il PC può svolgere contemporaneamente senza bloccarsi.
*   **Cache (L1, L2, L3):** memorie interne microscopiche ma ultra-veloci che aiutano la CPU a non dover sempre "pescare" i dati dalla memoria più lenta.

## 3. La Memoria RAM (Random Access Memory)
La RAM è la memoria di lavoro a breve termine. Avere più RAM permette di tenere aperti più programmi contemporaneamente senza rallentamenti. Non tutte le RAM sono uguali; per valutarle si guardano:
*   **Tipologia (Generazione):** le tecnologie oggi in commercio sono **DDR3, DDR4 e la più moderna DDR5**. Ogni tecnologia è riconoscibile dalla scanalatura presente sul modulo, vedi immagine.
*   **Frequenza:** viene espressa in **MHz**; più il numero è alto, più velocemente la RAM scambia dati con la CPU.
*   **Quantità:** si parte da un minimo di 4 GB fino ad arrivare a ben 128 GB per i grandi server aziendali. Per un uso lavorativo fluido o per giocare (gaming), oggi la quantità consigliata è di almeno **16 GB**.
*   **Latenza CAS:** un valore che indica i tempi di ritardo (meno ritardo c'è, meglio è).

![Differenze RAM](/informatica/ram-difference.jpg)

## 4. Le Memorie di Massa (Archiviazione)
A differenza della RAM, che si cancella spegnendo il PC, le memorie di massa conservano i dati per sempre. Esistono due opzioni principali:
*   **HDD (Hard Disk Drive):** i vecchi dischi meccanici, più economici ma decisamente più lenti.
*   **SSD (Solid State Drive):** dischi a stato solido senza parti meccaniche, raccomandati per installare il sistema operativo e i programmi perché molto più veloci. Se si desidera la massima reattività, i modelli **SSD NVMe** (che si collegano direttamente a uno slot dedicato sulla scheda madre) sono oggi la scelta migliore.

:::note[Lo sapevi che?]
Attualmente sono presenti 3 tipologie di SSD:
* **SSD SATA**: sono collegati alla scheda madre tramite un collegamento di tipo SATA (Serial ATA).
* **SSD PCIe**: sono collegati direttamente alla scheda madre in uno slot PCIe, più veloce di un collegamento SATA.
* **SSD NVMe**: sono collegati come gli SSD PCIe, ma in uno slot NVMe, la velocità è di gran lunga superiore ai due collegamenti precedenti, è il supporto più recente e utilizzato sui PC performanti.
:::

## 5. La Scheda Video (GPU)
La *Graphics Processing Unit* è la componente essenziale per elaborare la grafica 3D e i video. Chi usa videogiochi o fa grafica professionale ha bisogno di una scheda dedicata e potente. I due marchi leader in questo settore sono:
*   **NVIDIA GeForce:** molto diffuse sia per i videogiochi sia per il lavoro dei professionisti dell'immagine.
*   **AMD Radeon:** ottime alternative per il gaming e lo streaming.

## 6. L'Alimentatore (PSU) e il Raffreddamento
*   **L'alimentatore:** fornisce energia sicura e stabile a tutto il computer. Per sceglierlo si guarda la sua potenza in **Watt** (ne esistono da 500W, 750W, 1000W ecc. a seconda di quanti componenti energivori dobbiamo alimentare) e la sua **Certificazione di efficienza** (come *80 Plus Bronze, Gold o Platinum*), fondamentale per la sicurezza e la durata del PC.
*   **Il Raffreddamento:** i componenti sotto sforzo generano tantissimo calore. Esistono sistemi **ad aria** (più economici, usano ventole e dissipatori metallici) e sistemi **a liquido** (più costosi ma più efficienti, perfetti per chi gioca molto e fa lavorare il computer al massimo).

:::note[Nota]
La certificazione *80 Plus* è nata per promuovere l'efficienza degli alimentatori per PC:

Ogni alimentatore genera calore nel convertire la tensione della corrente di casa (in Italia è 240V in corrente alternata) in una tensione gestibile dalla scheda madre (dai 5 ai 12V in corrente continua).
Questo calore generato non viene utilizzato dal computer e si disperde nell'ambiente, per evitare un consumo inutile si dovrebbe prediligere degli alimentatori che siano il più efficienti possibile.
La certificazione 80 Plus, con i nomi assegnati (Bronze, Silver, Gold, Platinum, Titanium, Ruby), indicano un'efficienza che va dall'80% al 96% in base al carico.
:::

![80 Plus](/informatica/80-plus.jpg)