---
title: Rappresentazione dei numeri
description: La rappresentazione dei numeri nel calcolatore
---

## 1. Dal mondo reale al computer: Bit e Byte
I computer sono macchine elettroniche. Al loro interno, i dati viaggiano sotto forma di segnali elettrici. Per semplificare al massimo l'architettura e non commettere errori, i circuiti del calcolatore (essendo digitali e non analogici) riconoscono solo due stati logici ben distinti:
*   Presenza di tensione (acceso) $\rightarrow$ **1**
*   Assenza di tensione (spento) $\rightarrow$ **0**

Queste due cifre prendono il nome di **bit** (abbreviazione dell'inglese *binary digit*, ovvero "cifra binaria") e rappresentano l'unità di misura minima dell'informazione.
Poiché un solo bit può esprimere solo due valori (0 o 1), i computer raggruppano i bit in sequenze più lunghe. Il raggruppamento fondamentale è il **Byte**, composto da **8 bit**. Con un Byte, combinando zeri e uni, è possibile ottenere $2^8 = 256$ combinazioni diverse.

## 2. Il Sistema Decimale (Base 10)
Prima di capire il computer, ricordiamo come contiamo noi esseri umani. Noi usiamo il sistema decimale, chiamato "in base 10" perché utilizza 10 simboli (le cifre da **0 a 9**).
Il nostro è un **sistema posizionale**: il valore di ogni cifra dipende dalla posizione che occupa (unità, decine, centinaia, ecc.), che corrisponde a una potenza di 10.
Ad esempio, il numero $345$:

$345_{10} = 3 \cdot 10^2 + 4 \cdot 10^1 + 5 \cdot 10^0$

$345_{10} = 3 \cdot 100 + 4 \cdot 10 + 5 \cdot 1 = 300 + 40 + 5$

## 3. Il Sistema Binario (Base 2)
Il sistema binario è la lingua madre del computer. Utilizza solamente **2 simboli: 0 e 1**.
Anch'esso è un sistema posizionale, ma il "peso" di ogni posizione non è una potenza di 10, bensì una **potenza di 2** ($2^0, 2^1, 2^2, 2^3, \dots$).

### Da Binario a Decimale
Per tradurre un numero binario nella nostra lingua (decimale), basta moltiplicare ogni bit per la potenza di 2 corrispondente alla sua posizione (partendo da destra, dalla posizione 0) e sommare tutto.
Prendiamo il numero binario $1011_2$:

$1011_2 = 1 \cdot 2^3 + 0 \cdot 2^2 + 1 \cdot 2^1 + 1 \cdot 2^0$

$1011_2 = 1 \cdot 8 + 0 \cdot 4 + 1 \cdot 2 + 1 \cdot 1 = 8 + 0 + 2 + 1 = 11_{10}$

### Da Decimale a Binario (Metodo delle divisioni successive)
Per spiegare un nostro numero al computer, dobbiamo convertirlo in base 2. Il metodo più semplice è dividere continuamente il numero decimale per 2 e annotare i **resti**.
Convertiamo il numero $13_{10}$:
*   $13 / 2 = 6$ con resto di **1**
*   $6 / 2 = 3$ con resto di **0**
*   $3 / 2 = 1$ con resto di **1**
*   $1 / 2 = 0$ con resto di **1**

Una volta arrivati a 0, ci fermiamo e **leggiamo i resti dal basso verso l'alto**. Otteniamo così:
$13_{10} = 1101_2$

#### Esempio di conversione decimale $\rightarrow$ binario:

Vogliamo convertire il numero $345$ in binario.

Per ogni divisione per due segnamo alla destra il resto della divisione:

<div style="max-width: min(20%, 200px);">
    <img src="/rappresentazione-numeri/conversione-decimale-binario.png"/>
</div>

Il risultato finale, **partendo dal basso**, è $101011001$.

## 4. Il Sistema Esadecimale (Base 16)
I programmatori si sono accorti di un problema: scrivere numeri grandi in binario genera sequenze lunghissime e illeggibili per l'uomo (es. $110101101011_2$). Per "compattare" la scrittura, si usa molto il sistema **esadecimale (base 16)**.
Esso utilizza 16 simboli:
*   Le cifre da **0 a 9** (per i valori da zero a nove)
*   Le lettere da **A a F** per i valori successivi:
    *   $A = 10$, $B = 11$, $C = 12$, $D = 13$, $E = 14$, $F = 15$.

**Perché proprio il 16?** Perché $16 = 2^4$. Questo significa che **una singola cifra esadecimale corrisponde esattamente a 4 bit** (un *nibble*, cioè mezzo Byte).

### Da Esadecimale a Decimale
Il principio è identico a prima, ma usiamo le potenze di 16.

Esempio con $2F_{16}$:
* $2F_{16} = 2 \cdot 16^1 + 15 \cdot 16^0$
* $2F_{16} = 2 \cdot 16 + 15 \cdot 1 = 32 + 15 = 47_{10}$

### La magia: conversione diretta Binario ↔ Esadecimale
Convertire tra base 2 e base 16 è facilissimo, senza nemmeno passare per il decimale! Basta raggruppare i bit a gruppi di 4, partendo da destra.
Immagina di avere questo lungo Byte: $10110101_2$
1. Lo dividiamo in due blocchi da 4 bit: $1011$ e $0101$
2. Traduciamo ogni blocco:
    * $1011_2 = 8+0+2+1 = 11 \rightarrow \text{Che in esadecimale è } B$
    * $0101_2 = 0+4+0+1 = 5 \rightarrow \text{Che in esadecimale è } 5$
3. Uniamo il risultato: $10110101_2 = B5_{16}$

## 5. I numeri negativi
Finora abbiamo visto come tradurre in binario i numeri interi positivi, ma come fa il computer a capire se un numero è negativo, dato che non esiste il simbolo "$-$" nella memoria (ci sono solo $0$ e $1$)?

Esistono principalmente due metodi:

### Metodo 1: Modulo e Segno (Il metodo più intuitivo)
L'idea più semplice è usare il primo bit a sinistra (chiamato **bit più significativo**) come se fosse il simbolo del segno:
*   **$0$** significa positivo ($+$)
*   **$1$** significa negativo ($-$)

Se usiamo 4 bit in totale, il primo indica il segno e gli altri tre indicano il numero (il modulo).
Ad esempio:
*   $+5$ si scrive **$0$**$101$
*   $-5$ si scrive **$1$**$101$

*Il problema:* Questo metodo sembra perfetto, ma ha un difetto fastidioso per i computer. Esistono due modi per scrivere lo zero: $+0$ ($0000$) e $-0$ ($1000$). Inoltre, fare le operazioni matematiche (come le addizioni) con questo sistema complica molto i circuiti elettronici.

### Metodo 2: Il Complemento a Due (Il metodo usato dai computer)
Per risolvere i problemi del primo metodo, l'informatica moderna usa una tecnica molto più furba, chiamata **Complemento a due**.
Per trovare come scrivere un numero negativo (ad esempio $-5$), si seguono 3 semplici passi:
1.  **Si scrive il numero in positivo:** $+5 = 0101_2$
2.  **Si invertono tutti i bit** (gli $0$ diventano $1$, e gli $1$ diventano $0$): si ottiene $1010$ (questo passaggio si chiama *complemento a uno*).
3.  **Si aggiunge $1$ al risultato:** $1010 + 1 = 1011_2$

Quindi, per il computer, il numero $-5$ scritto su 4 bit è $1011_2$.
Il grande vantaggio di questo metodo è che lo zero ha un'unica rappresentazione ($0000$) e le sottrazioni possono essere calcolate dai circuiti del computer come se fossero delle semplici addizioni.

:::caution[Attenzione!]
Quando si lavora con il sistema di numerazione binario si può verificare il problema dell'**Overflowing**, cioè il superamento dei bit a disposizione.
Se l'overflow avviene quando si utilizzano i numeri negativi, un numero positivo diventerà negativo.

Esempio:

Abbiamo a disposizione solo 4 bit, quindi possiamo rappresentare i numeri da $-8_{10}$ a $7_{10}$.

Se sommiamo $2_{10}$ al numero $7_{10}$, con il sistema decimale otterremmo $9_{10}$, invece con il sistema binario otterremmo $1001_2$.

Proviamo a convertire il numero da complemento a due al binario e quindi al numero decimale corrispondente, facendo il procedimento inverso:
1. Sottraiamo $1$ dal numero $1001_2$ $\rightarrow$ $1000_2$
2. Invertiamo i bit $1000_2$ $\rightarrow$ $0111_2$
3. Convertiamo il numero $0111_2$ in decimale $\rightarrow$ $7_{10}$
4. Aggiungiamo il segno al risultato $\rightarrow$ $-7_{10}$ (dato che il numero aveva il bit del segno a $1$)

Come risultato abbiamo un numero negativo invece che positivo.
:::

## 6. I numeri con la virgola (Numeri Reali)
I numeri con la virgola (o numeri reali) aggiungono un livello di complessità: il computer deve sapere non solo quali sono le cifre, ma anche *dove si trova la virgola*.
Per farlo, si usa uno standard internazionale chiamato **Virgola Mobile** (in inglese *Floating Point*).

Il trucco della virgola mobile si basa sulla **notazione scientifica** che si studia in matematica e scienze. Ad esempio, invece di scrivere un numero enorme come $3.000.000$, scienziati e calcolatrici lo scrivono come $3 \cdot 10^6$. Allo stesso modo, un numero piccolissimo come $0,005$ diventa $5 \cdot 10^{-3}$.

Il computer fa la stessa identica cosa, ma usando le potenze di $2$ anziché di $10$. Per salvare un numero con la virgola, il computer prende lo spazio a disposizione (di solito 32 bit o 64 bit) e lo divide in **tre scompartimenti separati**:

1.  **Il Segno (1 bit):** Esattamente come prima, un solo bit fa da interruttore per indicare se l'intero numero è positivo ($0$) o negativo ($1$).
2.  **L'Esponente (8 bit):** Registra a quale potenza di due deve essere moltiplicato il numero (indica, in pratica, di quante posizioni e in che direzione la virgola deve "muoversi" o "galleggiare").
3.  **La Mantissa (23 bit):** Registra le cifre significative vere e proprie del numero, scritte rigorosamente come frazioni binarie.

**Esempio visivo su 32 bit (Singola Precisione - Standard IEEE 754):**
Immagina la memoria come una scatola lunga 32 bit:

`[S] [E E E E E E E E] [M M M M M M M M M M M M M M M M M M M M M M M]`
*   `S` = 1 bit per il segno.
*   `E` = 8 bit per l'esponente.
*   `M` = 23 bit per la mantissa.

Esistono anche il **Double Precision** (64 bit) e il **Quad Precision** (128 bit).

Grazie a questa organizzazione intelligente, un computer moderno riesce a rappresentare con altissima precisione sia numeri giganteschi (come le distanze tra le galassie) sia numeri infinitesimali (come le dimensioni di un atomo), usando sempre e solo zeri e uni.