---
title: Rappresentazione dei caratteri
description: La rappresentazione dei caratteri nel calcolatore
---

# La rappresentazione dei caratteri nel calcolatore

Per poter essere elaborati da un computer, i caratteri alfanumerici (lettere, numeri e simboli) devono essere trasformati in sequenze di bit. Questo processo prende il nome di codifica. A ogni carattere viene associato un numero univoco, che viene poi memorizzato in formato binario.

## 1. Il codice ASCII

### ASCII standard (7 bit)

Il primo standard universale diffuso è stato il codice ASCII (American Standard Code for Information Interchange). Nella sua versione originale, ASCII utilizzava 7 bit, permettendo di codificare $2^7 = 128$ caratteri (da 0 a 127).

*   **Vantaggi:** Risulta perfetto per la lingua inglese e per tutte le lingue che usano l'alfabeto latino (include lettere maiuscole, minuscole, cifre e punteggiatura base).
*   **Limiti:** Non include lettere accentate (à, è, ì, ò, ù) né simboli specifici di altre lingue. Per questo, paesi con alfabeti diversi dovrebbero adottare codifiche ASCII differenti, con conseguenti difficoltà in caso di comunicazioni che necessitano di simboli provenienti da diversi alfabeti.
    *   **Esempio:** Si immagini una pagina del libro digitale di matematica in cui compaiono simboli dell'alfabeto greco. Per codificare simboli di alfabeti diversi dovremmo usare sia ASCII latino sia la variante greca.

### ASCII esteso (8 bit)

Per ovviare alla mancanza di caratteri nazionali (come le lettere accentate, importanti in italiano ma inesistenti in inglese), si è passati all'utilizzo di 8 bit (1 Byte), raddoppiando le combinazioni possibili a $2^8 = 256$ (da 0 a 255). I primi 128 caratteri sono rimasti identici all'ASCII standard, mentre i successivi 128 (dal 128 al 255) sono stati utilizzati per simboli grafici, lettere greche e lettere accentate.

Tuttavia, la codifica a 8 bit ha un grande difetto: non esiste un unico standard (come d'altronde per ASCII standard 7 bit). L'ISO ha definito varie "Code Pages" per diverse regioni (es. una per l'Europa occidentale, una per l'alfabeto cirillico, una per l'alfabeto arabo). La conseguenza sta nel fatto che se un file scritto con una codifica viene letto da un PC con configurato un'altra, i caratteri estesi (cioè quelli oltre l'ASCII standard inglese) appaiono come simboli incomprensibili.

#### Tabella ASCII esteso (ISO Code Page 437)

Di seguito la tabella completa che mostra la corrispondenza tra valore decimale, binario e simbolo grafico.

| Cod. | Binario  | Car. | Cod. | Binario  | Car. | Cod. | Binario  | Car.   |
|:-----|:---------|:-----|:-----|:---------|:-----|:-----|:---------|:-------|
| 0    | 00000000 | NUL  | 86   | 01010110 | V    | 172  | 10101100 | ¼      |
| 1    | 00000001 | SOH  | 87   | 01010111 | W    | 173  | 10101101 | ¡      |
| 2    | 00000010 | STX  | 88   | 01011000 | X    | 174  | 10101110 | «      |
| 3    | 00000011 | ETX  | 89   | 01011001 | Y    | 175  | 10101111 | »      |
| 4    | 00000100 | EOT  | 90   | 01011010 | Z    | 176  | 10110000 | ░      |
| 5    | 00000101 | ENQ  | 91   | 01011011 | [    | 177  | 10110001 | ▒      |
| 6    | 00000110 | ACK  | 92   | 01011100 | \    | 178  | 10110010 | ▓      |
| 7    | 00000111 | BEL  | 93   | 01011101 | ]    | 179  | 10110011 | │      |
| 8    | 00001000 | BS   | 94   | 01011110 | ^    | 180  | 10110100 | ┤      |
| 9    | 00001001 | TAB  | 95   | 01011111 | _    | 181  | 10110101 | ╡      |
| 10   | 00001010 | LF   | 96   | 01100000 | `    | 182  | 10110110 | ╢      |
| 11   | 00001011 | VT   | 97   | 01100001 | a    | 183  | 10110111 | ╖      |
| 12   | 00001100 | FF   | 98   | 01100010 | b    | 184  | 10111000 | ╕      |
| 13   | 00001101 | CR   | 99   | 01100011 | c    | 185  | 10111001 | ╣      |
| 14   | 00001110 | SO   | 100  | 01100100 | d    | 186  | 10111010 | ║      |
| 15   | 00001111 | SI   | 101  | 01100101 | e    | 187  | 10111011 | ╗      |
| 16   | 00010000 | DLE  | 102  | 01100110 | f    | 188  | 10111100 | ╝      |
| 17   | 00010001 | DC1  | 103  | 01100111 | g    | 189  | 10111101 | ╜      |
| 18   | 00010010 | DC2  | 104  | 01101000 | h    | 190  | 10111110 | ╛      |
| 19   | 00010011 | DC3  | 105  | 01101001 | i    | 191  | 10111111 | ┐      |
| 20   | 00010100 | DC4  | 106  | 01101010 | j    | 192  | 11000000 | └      |
| 21   | 00010101 | NAK  | 107  | 01101011 | k    | 193  | 11000001 | ┴      |
| 22   | 00010110 | SYN  | 108  | 01101100 | l    | 194  | 11000010 | ┬      |
| 23   | 00010111 | ETB  | 109  | 01101101 | m    | 195  | 11000011 | ├      |
| 24   | 00011000 | CAN  | 110  | 01101110 | n    | 196  | 11000100 | ─      |
| 25   | 00011001 | EM   | 111  | 01101111 | o    | 197  | 11000101 | ┼      |
| 26   | 00011010 | SUB  | 112  | 01110000 | p    | 198  | 11000110 | ╞      |
| 27   | 00011011 | ESC  | 113  | 01110001 | q    | 199  | 11000111 | ╟      |
| 28   | 00011100 | FS   | 114  | 01110010 | r    | 200  | 11001000 | ╚      |
| 29   | 00011101 | GS   | 115  | 01110011 | s    | 201  | 11001001 | ╔      |
| 30   | 00011110 | RS   | 116  | 01110100 | t    | 202  | 11001010 | ╩      |
| 31   | 00011111 | US   | 117  | 01110101 | u    | 203  | 11001011 | ╦      |
| 32   | 00100000 | (sp) | 118  | 01110110 | v    | 204  | 11001100 | ╠      |
| 33   | 00100001 | !    | 119  | 01110111 | w    | 205  | 11001101 | ═      |
| 34   | 00100010 | "    | 120  | 01111000 | x    | 206  | 11001110 | ╬      |
| 35   | 00100011 | #    | 121  | 01111001 | y    | 207  | 11001111 | ╧      |
| 36   | 00100100 | $    | 122  | 01111010 | z    | 208  | 11010000 | ╨      |
| 37   | 00100101 | %    | 123  | 01111011 | {    | 209  | 11010001 | ╤      |
| 38   | 00100110 | &    | 124  | 01111100 | \|   | 210  | 11010010 | ╥      |
| 39   | 00100111 | '    | 125  | 01111101 | }    | 211  | 11010011 | ╙      |
| 40   | 00101000 | (    | 126  | 01111110 | ~    | 212  | 11010100 | ╘      |
| 41   | 00101001 | )    | 127  | 01111111 | DEL  | 213  | 11010101 | ╒      |
| 42   | 00101010 | *    | 128  | 10000000 | Ç    | 214  | 11010110 | ╓      |
| 43   | 00101011 | +    | 129  | 10000001 | ü    | 215  | 11010111 | ╫      |
| 44   | 00101100 | ,    | 130  | 10000010 | é    | 216  | 11011000 | ╪      |
| 45   | 00101101 | -    | 131  | 10000011 | â    | 217  | 11011001 | ┘      |
| 46   | 00101110 | .    | 132  | 10000100 | ä    | 218  | 11011010 | ┌      |
| 47   | 00101111 | /    | 133  | 10000101 | à    | 219  | 11011011 | █      |
| 48   | 00110000 | 0    | 134  | 10000110 | å    | 220  | 11011100 | ▄      |
| 49   | 00110001 | 1    | 135  | 10000111 | ç    | 221  | 11011101 | ▌      |
| 50   | 00110010 | 2    | 136  | 10001000 | ê    | 222  | 11011110 | ▐      |
| 51   | 00110011 | 3    | 137  | 10001001 | ë    | 223  | 11011111 | ▀      |
| 52   | 00110100 | 4    | 138  | 10001010 | è    | 224  | 11100000 | α      |
| 53   | 00110101 | 5    | 139  | 10001011 | ï    | 225  | 11100001 | ß      |
| 54   | 00110110 | 6    | 140  | 10001100 | î    | 226  | 11100010 | Γ      |
| 55   | 00110111 | 7    | 141  | 10001101 | ì    | 227  | 11100011 | π      |
| 56   | 00111000 | 8    | 142  | 10001110 | Ä    | 228  | 11100100 | Σ      |
| 57   | 00111001 | 9    | 143  | 10001111 | Å    | 229  | 11100101 | σ      |
| 58   | 00111010 | :    | 144  | 10010000 | É    | 230  | 11100110 | μ      |
| 59   | 00111011 | ;    | 145  | 10010001 | æ    | 231  | 11100111 | τ      |
| 60   | 00111100 | <    | 146  | 10010010 | Æ    | 232  | 11101000 | Φ      |
| 61   | 00111101 | =    | 147  | 10010011 | ô    | 233  | 11101001 | Θ      |
| 62   | 00111110 | >    | 148  | 10010100 | ö    | 234  | 11101010 | Ω      |
| 63   | 00111111 | ?    | 149  | 10010101 | ò    | 235  | 11101011 | δ      |
| 64   | 01000000 | @    | 150  | 10010110 | û    | 236  | 11101100 | ∞      |
| 65   | 01000001 | A    | 151  | 10010111 | ù    | 237  | 11101101 | φ      |
| 66   | 01000010 | B    | 152  | 10011000 | ÿ    | 238  | 11101110 | ε      |
| 67   | 01000011 | C    | 153  | 10011001 | Ö    | 239  | 11101111 | ∩      |
| 68   | 01000100 | D    | 154  | 10011010 | Ü    | 240  | 11110000 | ≡      |
| 69   | 01000101 | E    | 155  | 10011011 | ¢    | 241  | 11110001 | ±      |
| 70   | 01000110 | F    | 156  | 10011100 | £    | 242  | 11110010 | ≥      |
| 71   | 01000111 | G    | 157  | 10011101 | ¥    | 243  | 11110011 | ≤      |
| 72   | 01001000 | H    | 158  | 10011110 | ₧    | 244  | 11110100 | ⌠      |
| 73   | 01001001 | I    | 159  | 10011111 | ƒ    | 245  | 11110101 | ⌡      |
| 74   | 01001010 | J    | 160  | 10100000 | á    | 246  | 11110110 | ÷      |
| 75   | 01001011 | K    | 161  | 10100001 | í    | 247  | 11110111 | ≈      |
| 76   | 01001100 | L    | 162  | 10100010 | ó    | 248  | 11111000 | °      |
| 77   | 01001101 | M    | 163  | 10100011 | ú    | 249  | 11111001 | ∙      |
| 78   | 01001110 | N    | 164  | 10100100 | ñ    | 250  | 11111010 | ·      |
| 79   | 01001111 | O    | 165  | 10100101 | Ñ    | 251  | 11111011 | √      |
| 80   | 01010000 | P    | 166  | 10100110 | ª    | 252  | 11111100 | ⁿ      |
| 81   | 01010001 | Q    | 167  | 10100111 | º    | 253  | 11111101 | ²      |
| 82   | 01010010 | R    | 168  | 10101000 | ¿    | 254  | 11111110 | ■      |
| 83   | 01010011 | S    | 169  | 10101001 | ⌐    | 255  | 11111111 | (nbsp) |
| 84   | 01010100 | T    | 170  | 10101010 | ¬    |      |          |        |
| 85   | 01010101 | U    | 171  | 10101011 | ½    |      |          |        |

**Curiosità:** Se premi il tasto "1" sulla tastiera, il computer non vede il numero 1 (00000001 bin), ma riceve il codice ASCII del carattere '1', che è 49 (00110001 bin).

## 2. La rivoluzione Unicode

La limitazione a 256 caratteri dell'ASCII esteso rendeva impossibile rappresentare in un unico documento lingue diverse (es. italiano e giapponese insieme). Inoltre, lingue come il cinese o il giapponese utilizzano migliaia di ideogrammi, ben oltre la capacità di 8 bit.

Nel 1991 è stato introdotto lo standard Unicode, basato sull'idea di assegnare un codice univoco a ogni carattere di ogni lingua umana, inclusi gli ideogrammi (CJK - Cinese, Giapponese, Coreano) e i simboli moderni (come le Emoji). La struttura di ogni codifica si compone di 16 bit, permettendo così la rappresentazione di 65536 caratteri.

Sebbene risolva il problema della limitata espressività di ASCII esteso, usare sempre 16 bit (2 Byte) anche per i semplici caratteri inglesi (che ne richiederebbero solo 1) porta a uno spreco di memoria significativo nei file di testo occidentali.

*   **Esempio:** Un documento di testo contenente 1000 volte la parola "ciao" pesa $1 \times 4 \times 1000 = 4000$ Byte con ASCII esteso, ma il suo peso diventa $2 \times 4 \times 1000 = 8000$ Byte con UNICODE!

## 3. Le codifiche UTF: efficienza e compatibilità

Per bilanciare la necessità di rappresentare tutti i caratteri del mondo con l'esigenza di risparmiare spazio, sono nate le codifiche UTF (Unicode Transformation Format). La più diffusa è UTF-8. È una codifica a lunghezza variabile (1-6 Byte):

*   I 127 caratteri base (quelli dell'ASCII standard) occupano 1 solo Byte. Questo garantisce retrocompatibilità totale con i vecchi sistemi ASCII.
*   Le lettere accentate e altri simboli latini usano 2 Byte.
*   Gli ideogrammi e altri simboli complessi usano 3 o 4 Byte (fino a un massimo teorico di 6 Byte in vecchie specifiche, ma comunemente 4).

In questo modo, i caratteri più frequenti sono mappati su codifiche più corte e si ottiene quindi un notevole risparmio dello spazio rispetto a UNICODE (più sono presenti caratteri di uso poco frequente e minore è il risparmio che si ottiene... ma quante volte navigando sul web visitate pagine scritte in giapponese???).

### Come funziona UTF-8?

UTF-8 ha un'altra importante caratteristica: è un codice autodescrittente, poiché il computer capisce quanti Byte leggere guardando i primi bit del primo Byte:

*   Se inizia con `0`... => è un solo Byte (ASCII standard).
*   Se inizia con `110`... => il carattere è composto da 2 Byte.
*   Se inizia con `1110`... => il carattere è composto da 3 Byte.

Oggi UTF-8 è lo standard de facto per il web e i moderni sistemi operativi, unendo l'efficienza dell'ASCII alla completezza di Unicode.

## 4. Caso pratico: lettera "à"

Per comprendere meglio le differenze di spazio e compatibilità, vediamo come viene memorizzata la lettera minuscola accentata "à" nelle diverse codifiche.

| Standard                  | Supportato? | Codifica binaria (in memoria) | Spazio occupato | Note                                                                     |
|:--------------------------|:------------|:------------------------------|:----------------|:-------------------------------------------------------------------------|
| ASCII Base (7 bit)        | ❌ NO        | Impossibile rappresentare     | -               | Il codice arriva solo fino a 127.                                        |
| ASCII Esteso (CP 437)     | ✅ SÌ        | `10000101`                    | 1 Byte          | Valido solo se il computer usa la tabella DOS/OEM (valore decimale 133). |
| Unicode (16 bit standard) | ✅ SÌ        | `00000000 11100000`           | 2 Byte          | Usa sempre 16 bit, anche se il carattere starebbe su 8 bit.              |
| UTF-8                     | ✅ SÌ        | `11000011 10100000`           | 2 Byte          | Richiede 2 Byte perché è un carattere non-ASCII standard.                |