---
title: Operatori Logici e Algebra Booleana
description: Come il calcolatore effettua le operazioni logiche
---

## L'Algebra Booleana e gli Operatori Logici

Come abbiamo già visto nella rappresentazione dei numeri, i computer ragionano unicamente riconoscendo due stati elettrici: presenza di tensione (**1**) o assenza di tensione (**0**). Ma come fa una macchina a prendere decisioni intelligenti usando solo zeri e uni? È qui che entra in gioco l'**Algebra Booleana**.

Inventata dal matematico inglese George Boole a metà dell'Ottocento (molto prima dell'invenzione dei computer!), questa particolare matematica non usa i numeri tradizionali con infinite cifre, ma lavora unicamente con due "valori di verità":
*   **Vero** (True), che nel computer corrisponde al bit **1**.
*   **Falso** (False), che nel computer corrisponde al bit **0**.

Nell'algebra booleana, le variabili (che indichiamo con lettere maiuscole come $A$, $B$ o $C$) possono valere solo $0$ oppure $1$. Per combinare queste variabili e fare dei calcoli, non usiamo le classiche operazioni come la sottrazione o la divisione, ma degli speciali **operatori logici** (chiamati anche *porte logiche* nell'elettronica).

I tre operatori fondamentali sono **NOT**, **AND** e **OR**. Per capire esattamente come funzionano si usano le **Tabelle della Verità**, cioè degli schemi riassuntivi che mostrano tutti i possibili risultati di un'operazione logica al variare dei dati in ingresso (input).

### 1. L'operatore NOT (Negazione logica)
L'operatore NOT è il più semplice: prende un singolo valore e lo inverte (lo "nega"). Se il valore in ingresso è Vero, il risultato diventa Falso. Se è Falso, diventa Vero.

In matematica si indica spesso mettendo un trattino sopra la lettera ($\bar{A}$) oppure con uno speciale simbolo davanti ($\neg A$).

**Tabella della Verità del NOT:**
| $A$ (Input) | $\bar{A}$ (Risultato / Output) |
| :---: | :---: |
| 0 | **1** |
| 1 | **0** |

### 2. L'operatore AND (Prodotto logico)
L'operatore AND (in italiano "E") confronta due variabili. La regola è severissima: il risultato è **Vero (1) solamente se TUTTE E DUE le variabili sono Vere**. In tutti gli altri casi il risultato è Falso (0).

Si indica col simbolo del prodotto matematico ($A \cdot B$) o con una "V" rovesciata ($A \land B$).

*Esempio per capire:* Immagina di dover aprire una cassaforte. La porta si apre (Risultato = 1) solo se hai inserito il codice corretto ($A$) **AND** hai girato la chiave logica ($B$). Se ne manca anche solo uno, la cassaforte non si apre!

**Tabella della Verità dell'AND:**
| $A$ | $B$ | $A \cdot B$ (A AND B) |
| :---: | :---: | :---: |
| 0 | 0 | **0** |
| 0 | 1 | **0** |
| 1 | 0 | **0** |
| 1 | 1 | **1** |

### 3. L'operatore OR (Somma logica)
L'operatore OR (in italiano "O / Oppure") confronta due variabili, ma è molto più permissivo dell'AND: il risultato è **Vero (1) se ALMENO UNA delle due variabili è Vera**. Risulta Falso solo ed esclusivamente se entrambe sono false.
Si indica col simbolo della somma ($A + B$) o con una "V" diritta ($A \lor B$).

*Esempio per capire:* Immagina una stanza buia con due interruttori della luce. La stanza si illumina (Risultato = 1) se premi il primo interruttore ($A$) **OR** se premi il secondo ($B$), o anche se li premi entrambi contemporaneamente.

**Tabella della Verità dell'OR:**
| $A$ | $B$ | $A + B$ (A OR B) |
| :---: | :---: | :---: |
| 0 | 0 | **0** |
| 0 | 1 | **1** |
| 1 | 0 | **1** |
| 1 | 1 | **1** |

### 4. Le Espressioni Booleane e il computer
Proprio come nella normale algebra, possiamo combinare questi operatori per creare istruzioni (espressioni) via via più complesse, usando le parentesi per dare la precedenza.
Ad esempio, l'espressione $Y = (A \cdot B) + \bar{C}$ significa che il risultato $Y$ sarà vero se $A$ e $B$ sono entrambi veri, **oppure** se $C$ è falso.

Perché tutto questo è così importante in informatica? Perché il processore (la CPU) del tuo computer, o del tuo smartphone, non è altro che un microscopico labirinto composto da miliardi di queste porte logiche (AND, OR e NOT) fatte di silicio. Lavorando insieme alla velocità della luce, questi semplici operatori riescono a eseguire calcoli elaborati, farti navigare su Internet o far funzionare un videogioco tridimensionale.

## Gli Operatori Derivati: XOR, NAND e NOR
Oltre ai tre operatori fondamentali (NOT, AND, OR), l'algebra booleana e l'elettronica dei computer utilizzano altri operatori molto utili. Si chiamano "derivati" perché si ottengono combinando tra loro quelli di base. I tre più importanti sono lo **XOR**, il **NAND** e il **NOR**.

### L'operatore XOR (OR Esclusivo)
L'operatore XOR (dall'inglese *eXclusive OR*) è uno degli operatori più usati in informatica, specialmente per fare i calcoli binari e nella crittografia (per proteggere i dati).
La sua regola è semplice: il risultato è **Vero (1) SOLAMENTE se le due variabili sono DIVERSE tra loro**. Se le variabili sono uguali (entrambe vere o entrambe false), il risultato è Falso (0).
In matematica si indica con il simbolo di un più racchiuso in un cerchio: $A \oplus B$.

*Esempio per capire:* Immagina la proposta: "Stasera puoi avere il gelato ($A$) **o** la fetta di torta ($B$)". Questa frase sottintende un "OR esclusivo": puoi scegliere uno dei due dolci, ma non puoi averli entrambi, e non puoi nemmeno rimanere senza!

**Tabella della Verità dello XOR:**
| $A$ | $B$ | $A \oplus B$ (A XOR B) |
| :---: | :---: | :---: |
| 0 | 0 | **0** |
| 0 | 1 | **1** |
| 1 | 0 | **1** |
| 1 | 1 | **0** |

### L'operatore NAND (NOT + AND)
Come suggerisce il nome, il NAND non è altro che un operatore AND a cui è stato attaccato un NOT alla fine. Fa esattamente **l'opposto dell'AND**.
Se l'AND era vero solo quando entrambe le variabili erano vere, il NAND è **Vero (1) in tutti i casi, TRANNE quando entrambe le variabili sono vere**.
Si indica prendendo il simbolo dell'AND e mettendoci sopra una barra di negazione: $\overline{A \cdot B}$.

*Curiosità tecnica:* Il NAND è considerato un operatore "universale". Questo significa che, collegando tra loro tante porte logiche NAND, i costruttori di microprocessori possono ricreare la funzione di qualsiasi altro operatore (NOT, OR, AND). Usare un solo tipo di porta logica per costruire un'intera CPU abbatte enormemente i costi di produzione!

**Tabella della Verità del NAND:**
| $A$ | $B$ | $\overline{A \cdot B}$ (A NAND B) |
| :---: | :---: | :---: |
| 0 | 0 | **1** |
| 0 | 1 | **1** |
| 1 | 0 | **1** |
| 1 | 1 | **0** |

### L'operatore NOR (NOT + OR)
In modo del tutto simile al NAND, il NOR è l'esatto **opposto dell'OR**.
Essendo la negazione della somma logica, il suo risultato è **Vero (1) SOLO quando ENTRAMBE le variabili sono False (0)**. In tutti gli altri casi, in cui compare almeno un 1, il risultato precipita a zero.
Si indica mettendo la barra di negazione sopra l'operazione OR: $\overline{A + B}$.

**Tabella della Verità del NOR:**
| $A$ | $B$ | $\overline{A + B}$ (A NOR B) |
| :---: | :---: | :---: |
| 0 | 0 | **1** |
| 0 | 1 | **0** |
| 1 | 0 | **0** |
| 1 | 1 | **0** |