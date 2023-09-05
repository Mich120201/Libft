# $${\color{red}Libft}$$

Libft è una libreria contenente le maggiori funzioni utilizzate nel linguaggio C, sono funzioni ricreate a mano in modo che riproduca lo stesso risultato o quasi.

## $${\color{orange}FtAtoi}$$

### $${\color{yellow}Descrizione}$$

Funzione che nel linguaggio C si trova nella libreria <stdlib.h>. Serve per convertire un argomento di tipo STR in un argomento di tipo INT.

### $${\color{yellow}Dichiarazione}$$

Essa è dicharata in questo modo:

$${\color{white}int \space \color{white}atoi(const \space \color{white}char \space \color{white}*str)}$$

La replica di questa funzione in questa libreria è dichiarata in questa maniera:

$${\color{white}int \space \color{white}ft \space \color{white}atoi(const \space \color{white}char \space \color{white}*str)}$$

### $${\color{yellow}Parametri}$$

Il parametro che viene richiesto di essere passato è "str", una stringa di tipo const, che verra conventita nella nostra funzione.

### $${\color{yellow}Valore \space \color{yellow}di \space \color{yellow}ritorno}$$

La funzione restituisce la variabile convertita in tipo INT, se non c'è alcuna implementazione di una conversion eefficacie la funzione restituisce 0.

### $${\color{yellow}Analisi \space \color{yellow}funzione}$$

All'inizio della funzione dichiariamo tre variabili: i, s, res. la varibile i serve com indice per mouversi lungo la stringa carattere per carattere, s ci servira per fare i calcoli e la variabile res per salavre il risultato finale che verra poi ritornato. 

Poi ci serviamo di un ciclo "while" per saltare eventuali caratteri che non possono essere considerati nella conversione come "\t", "\r" e lo spazio, poi controlliamo che i valori passati sono positivi o negativi.

Poi con un altro ciclo "while" passiamo di carattere in carattere per convertirli poco alla volta con questa operazione: "res = (str[i] - '0') + (res * 10)". Questa operazione fa in modo che il carattere contenuto in str[i] che durante il ciclo ci assicuriamo sia tra '0' e '9' e da sottraiamo '0' in modo da farci restituire precisamente il valore intero corrispondante, ad esempio se all'interno di str[i] è contenuto '5' facendo questa sottrazione verrebero dalla macchina sostituiti con i loro caratteri ascii, quindi l'operazione risulterebbe in questo caso 53('5')-48('0') che restituisce 5. Poi lo sommianmo a res moltiplicato per 10 che serve a spostare le cifre dento res di 1 a sinistra in modo da far spazio per la nuova cifra.

Infine facciamo un semplice controllo su res per essere sicuri che non superi il limite massimo o minimo della variabile tipo int, il massimo è 2147483647 mentre il minimo -2147483647, in caso uno di questi due numeri venga superato restiuiamo solo questo numero 2147483647 in negativo o positivo per assicurarci che il programma non vada in errore.
