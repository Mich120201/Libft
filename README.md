# $${\color{ballblue}Libft}$$

Libft è una libreria contenente le maggiori funzioni utilizzate nel linguaggio C, sono funzioni ricreate a mano in modo che riproduca lo stesso risultato o quasi.

## $${\color{cyan}FtAtoi}$$

### $${\color{lightblue}Descrizione}$$

Funzione che nel linguaggio C si trova nella libreria <stdlib.h>. Serve per convertire un argomento di tipo STR in un argomento di tipo INT.

### $${\color{lightblue}Dichiarazione}$$

Essa è dicharata in questo modo:

<code style="color : green">int atoi(const char *str)</code>

La replica di questa funzione in questa libreria è dichiarata in questa maniera:

<code style="color : green">int	ft_atoi(const char *str)</code>

### $${\color{lightblue}Parametri}$$

Il parametro che viene richiesto di essere passato è <code style="color : green">"str"</code>, una stringa di tipo const, che verra conventita nella nostra funzione.

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

La funzione restituisce la variabile convertita in tipo <code style="color : green">INT</code>, se non c'è alcuna implementazione di una conversion eefficacie la funzione restituisce 0.

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

All'inizio della funzione dichiariamo tre variabili: <code style="color : green">i</code>, <code style="color : green">s</code>, <code style="color : green">res</code>. la varibile <code style="color : green">i</code> serve come indice per mouversi lungo la stringa carattere per carattere, <code style="color : green">s</code> ci servira per fare i calcoli e la variabile <code style="color : green">res</code> per salavre il risultato finale che verra poi ritornato. 

Poi ci serviamo di un ciclo "while" per saltare eventuali caratteri che non possono essere considerati nella conversione come <code style="color : green">"\t"</code>, <code style="color : green">"\r"</code> e lo <code style="color : green">spazio</code>, poi controlliamo che i valori passati sono <code style="color : green">positivi</code> o <code style="color : green">negativi</code>.

Poi con un altro ciclo <code style="color : green">"while"</code> passiamo di carattere in carattere per convertirli poco alla volta con questa operazione: <code style="color : green">"res = (str[i] - '0') + (res * 10)"</code>. Questa operazione fa in modo che il carattere contenuto in <code style="color : green">str[i]</code> che durante il ciclo ci assicuriamo sia tra <code style="color : green">'0'</code> e <code style="color : green">'9'</code> e da esso poi sottraiamo '0' in modo da farci restituire precisamente il valore intero corrispondante, ad esempio se all'interno di <code style="color : green">str[i]</code> è contenuto '5' facendo questa sottrazione verrebero dalla macchina sostituiti con i loro caratteri ascii, quindi l'operazione risulterebbe in questo caso <code style="color : green">53('5')-48('0')</code> che restituisce 5. Poi lo sommianmo a <code style="color : green">res</code> moltiplicato per 10 che serve a spostare le cifre dentro <code style="color : green">res</code> di 1 a sinistra in modo da far spazio per la nuova cifra.

Infine facciamo un semplice controllo su <code style="color : green">res</code> per essere sicuri che non superi il limite massimo o minimo della variabile tipo int, il massimo è <code style="color : green">2147483647</code> mentre il minimo <code style="color : green">-2147483647</code>, in caso uno di questi due numeri venga superato restiuiamo solo questo numero <code style="color : green">2147483647</code> in <code style="color : green">positivo</code> o <code style="color : green">negativo</code> per assicurarci che il programma non vada in errore.
