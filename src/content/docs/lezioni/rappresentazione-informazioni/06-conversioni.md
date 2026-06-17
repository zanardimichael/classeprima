---
title: Conversioni tra sistemi di numerazione
---

Sappiamo già che noi esseri umani contiamo in **Decimale (Base 10)**, i computer ragionano in **Binario (Base 2)**, e i programmatori usano sistemi più compatti come l'**Esadecimale (Base 16)** o l'**Ottale (Base 8)**. Ma come si passa da un sistema all'altro?

# Guida Pratica alle Conversioni tra Sistemi di Numerazione

Per non perderci in un mare di numeri, divideremo le conversioni in **tre grandi "famiglie"**. Imparando il metodo per ogni famiglia, sarete in grado di tradurre qualsiasi numero.

## Famiglia 1: Dal sistema Decimale agli altri sistemi (Metodo delle divisioni successive)
Per spiegare un nostro numero decimale al computer, dobbiamo "smontarlo". Il metodo universale consiste nel **dividere continuamente il numero decimale per la base di destinazione** (2, 8 o 16) e annotare i **resti**. Alla fine, i resti letti dal basso verso l'alto formeranno il nostro nuovo numero!

### **Da Decimale a Binario (Base 2):** 

Dividiamo per 2.

Convertiamo $13_{10}$:
*   $13 / 2 = 6$ con resto di **$1$**
*   $6 / 2 = 3$ con resto di **$0$**
*   $3 / 2 = 1$ con resto di **$1$**
*   $1 / 2 = 0$ con resto di **$1$**

Leggendo i resti dal basso verso l'alto: $13_{10} = 1101_2$.

### **Da Decimale a Ottale (Base 8):** 

Dividiamo per 8.

Convertiamo $37_{10}$:
*   $37 / 8 = 4$ con resto di **$5$**
*   $4 / 8 = 0$ con resto di **$4$**
    
Leggendo dal basso verso l'alto: $37_{10} = 45_8$.

*   **Da Decimale a Esadecimale (Base 16):** Dividiamo per 16.
    *Attenzione:* ricordatevi che i resti da $10$ a $15$ si scrivono con le lettere da $A$ a $F$!
    Convertiamo $47_{10}$:
    *   $47 / 16 = 2$ con resto di $15$ (che equivale a **$F$**)
    *   $2 / 16 = 0$ con resto di **$2$**
    
    Leggendo dal basso verso l'alto: $47_{10} = 2F_{16}$.

## Famiglia 2: Dagli altri sistemi al sistema Decimale (Metodo delle potenze)
Quando il computer deve mostrare un numero sul monitor per farcelo capire, fa l'operazione inversa. Dato che tutti questi sistemi sono "posizionali", basta moltiplicare ogni cifra per la **potenza della sua base**, partendo sempre dalla posizione zero a destra, e infine sommare tutto.

### **Da Binario a Decimale:** 

Usiamo le potenze di 2.

Convertiamo $1011_2$:
* $1011_2 = 1 \cdot 2^3 + 0 \cdot 2^2 + 1 \cdot 2^1 + 1 \cdot 2^0$
* $1011_2 = 1 \cdot 8 + 0 \cdot 4 + 1 \cdot 2 + 1 \cdot 1 = 8 + 0 + 2 + 1 = 11_{10}$.

### **Da Ottale a Decimale:** 

Usiamo le potenze di 8.

Convertiamo $45_8$:
* $45_8 = 4 \cdot 8^1 + 5 \cdot 8^0$
* $45_8 = 4 \cdot 8 + 5 \cdot 1 = 32 + 5 = 37_{10}$.

### **Da Esadecimale a Decimale:** 

Usiamo le potenze di 16.

Convertiamo $2F_{16}$:
* $2F_{16} = 2 \cdot 16^1 + 15 \cdot 16^0$
* $2F_{16} = 2 \cdot 16 + 15 \cdot 1 = 32 + 15 = 47_{10}$.

## Famiglia 3: Le conversioni dirette ("magiche")
L'ottale e l'esadecimale sono nati per raggruppare i lunghissimi numeri binari. Poiché $16 = 2^4$ e $8 = 2^3$, possiamo fare conversioni istantanee senza mai fare calcoli complessi, semplicemente dividendo il numero binario in "pacchetti".

### **Da Binario a Esadecimale:** 

Raggruppiamo i bit a **gruppi di 4**, partendo da destra.

* $10110101_2 \rightarrow$ dividiamo in $1011$ e $0101$.
* $1011_2 = 11_{10} = B_{16}$.
* $0101_2 = 5_{10} = 5_{16}$.

Risultato: $B5_{16}$.

:::note[Nota]
*Per fare il contrario, da **Esadecimale a Binario**, basta esplodere ogni cifra esadecimale in 4 bit! Es. $B5_{16} \rightarrow B=1011_2, 5=0101_2 \rightarrow 10110101_2$*.
:::

### **Da Binario a Ottale:** 

Raggruppiamo i bit a **gruppi di 3**, partendo da destra.

* $101110_2 \rightarrow$ dividiamo in $101$ e $110$.
* $101_2 = 5_8$.
* $110_2 = 6_8$.

Risultato: $56_8$.

:::note[Nota]
*Allo stesso modo, per il passaggio inverso da **Ottale a Binario**, traduciamo ogni singola cifra in un pacchetto esatto di 3 bit*.
:::

## Il caso speciale: Conversione tra Esadecimale e Ottale (e viceversa)
E se vi chiedessi di passare direttamente dalla base 16 alla base 8?
Qui c'è un trucco da veri informatici: **non esiste un calcolo diretto facile!**
Il metodo più sicuro e veloce è usare il sistema binario come **"ponte"**.

### **Da Esadecimale a Ottale:**

1. Trasformiamo l'esadecimale in binario (esplodendo in pacchetti da 4 bit).
2. Raggruppiamo il binario ottenuto in pacchetti da 3 bit per trovare l'ottale!
    
*Esempio:* Convertiamo $2F_{16}$ in ottale.
* $2 \rightarrow 0010_2$ e $F \rightarrow 1111_2$. Il binario è $00101111_2$.
* Ora creiamo gruppi da 3 partendo da destra: $000$ (aggiungiamo uno zero per riempire), $101$, $111$.
* Traduciamo: $0_8$, $5_8$, $7_8$. Risultato finale: $57_8$.

### **Da Ottale a Esadecimale:**

Facciamo il viaggio al contrario!
1. Trasformiamo l'ottale in binario (esplodendo in pacchetti da 3 bit).
2. Raggruppiamo il binario in pacchetti da 4 bit per trovare l'esadecimale!
    
*Esempio:* Convertiamo $57_8$ in esadecimale.
* $5 \rightarrow 101_2$ e $7 \rightarrow 111_2$. Il binario è $101111_2$.
* Ora creiamo gruppi da 4 partendo da destra: $0010$ (aggiungendo due zeri), $1111$.
* Traduciamo: $0010_2 = 2_{16}$, $1111_2 = F_{16}$. Risultato finale: $2F_{16}$.