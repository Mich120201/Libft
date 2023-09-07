# $${\color{Aquamarine}Libft}$$

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

Richiede un argomento, <code style="color : green">str</code>, una stringa di tipo const, che verra conventita nella nostra funzione.

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

La funzione restituisce la variabile convertita in tipo <code style="color : green">INT</code>, se non c'è alcuna implementazione di una conversion eefficacie la funzione restituisce 0.

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

All'inizio della funzione dichiariamo tre variabili: <code style="color : green">i</code>, <code style="color : green">s</code>, <code style="color : green">res</code>. la varibile <code style="color : green">i</code> serve come indice per mouversi lungo la stringa carattere per carattere, <code style="color : green">s</code> ci servira per fare i calcoli e la variabile <code style="color : green">res</code> per salavre il risultato finale che verra poi ritornato. 

Poi ci serviamo di un ciclo "while" per saltare eventuali caratteri che non possono essere considerati nella conversione come <code style="color : green">"\t"</code>, <code style="color : green">"\r"</code> e lo <code style="color : green">spazio</code>, poi controlliamo che i valori passati sono <code style="color : green">positivi</code> o <code style="color : green">negativi</code>.

Poi con un altro ciclo <code style="color : green">"while"</code> passiamo di carattere in carattere per convertirli poco alla volta con questa operazione: <code style="color : green">"res = (str[i] - '0') + (res * 10)"</code>. Questa operazione fa in modo che il carattere contenuto in <code style="color : green">str[i]</code> che durante il ciclo ci assicuriamo sia tra <code style="color : green">'0'</code> e <code style="color : green">'9'</code> e da esso poi sottraiamo '0' in modo da farci restituire precisamente il valore intero corrispondante, ad esempio se all'interno di <code style="color : green">str[i]</code> è contenuto '5' facendo questa sottrazione verrebero dalla macchina sostituiti con i loro caratteri ascii, quindi l'operazione risulterebbe in questo caso <code style="color : green">53('5')-48('0')</code> che restituisce 5. Poi lo sommianmo a <code style="color : green">res</code> moltiplicato per 10 che serve a spostare le cifre dentro <code style="color : green">res</code> di 1 a sinistra in modo da far spazio per la nuova cifra.

Infine facciamo un semplice controllo su <code style="color : green">res</code> per essere sicuri che non superi il limite massimo o minimo della variabile tipo int, il massimo è <code style="color : green">2147483647</code> mentre il minimo <code style="color : green">-2147483647</code>, in caso uno di questi due numeri venga superato restiuiamo solo questo numero <code style="color : green">2147483647</code> in <code style="color : green">positivo</code> o <code style="color : green">negativo</code> per assicurarci che il programma non vada in errore.

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtBzero}$$

### $${\color{lightblue}Descrizione}$$

Funzione che nel linguaggio C si trova nella libreria <strings.h>. La funzione bzero può essere usata per cancellare la data area di memoria con </code style="color : green">zero byte(\0)</code>.

### $${\color{lightblue}Dichiarazione}$$

Essa è dicharata in questo modo:

<code style="color : green">void bzero(void *s, size_t n)</code>

La replica di questa funzione in questa libreria è dichiarata in questa maniera:

<code style="color : green">void	ft_bzero(void *s, size_t n)</code>

### $${\color{lightblue}Parametri}$$

Richiede due argomenti, l’</code style="color : green">indirizzo iniziale della regione di memoria</code> e il </code style="color : green">numero di byte</code> che devono essere azzerati.

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

La funzione ft_bzero non ha nessun valore di ritorno.

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

In questa funzione prendiamo due variabili durante la dichiarazione e le passiamo alla funzion </code style="color : green">memset</code>.

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtCalloc}$$

### $${\color{lightblue}Descrizione}$$

Funzione che nel linguaggio C si trova nella libreria <stdlib.h> e <malloc.h>. Questa funzione alloca meoria in modo dimanico.

### $${\color{lightblue}Dichiarazione}$$

Essa è dicharata in questo modo:

<code style="color : green">void *calloc(size_t number, size_t size)</code>

La replica di questa funzione in questa libreria è dichiarata in questa maniera:

<code style="color : green">void	*ft_calloc(size_t nmemb, size_t size)</code>

### $${\color{lightblue}Parametri}$$

Richiede due argomenti, </code style="color : green">number</code> il numero di elementi da allocare e </code style="color : green">size</code> la lunghezza di ogni elemento.

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

Calloc restituisce un puntatore allo </code style="color : green">spazio allocato</code>. Lo spazio di archiviazione a cui punta il valore restituito è allineato in modo adeguato per l'</code style="color : green">archiviazione</code> di qualsiasi tipo di oggetto.

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

Nella nostra funzione dichiariamo una variabile <code style="color : green">void *</code> che utilizziamo per allocare la memoria attraverso la funzione <code style="color : green">malloc</code> a cui passiamo il parametro <code style="color : green">nmemb</code> moltiplicato per <code style="color : green">size</code>.

Dopo aver controllato che l'allocazione sia andata a buon fine utilizziml la funzione <code style="color : green">ft_bzero</code> a cui passiamo <code style="color : green">mem</code> e <code style="color : green">nmemb</code> moltiplicato per <code style="color : green">size</code>.

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtIsalnum}$$

### $${\color{lightblue}Descrizione}$$

Funzione che nel linguaggio C si trova nella libreria <ctype.h>. Questa funzione controlla che l'argomento passato sia una lettera dell'alfabeto e un numero.

### $${\color{lightblue}Dichiarazione}$$

Essa è dicharata in questo modo:

<code style="color : green">int isalnum(int argument)</code>

La replica di questa funzione in questa libreria è dichiarata in questa maniera:

<code style="color : green">int	ft_isalnum(int c)</code>

### $${\color{lightblue}Parametri}$$

Richiede un solo argomento, </code style="color : green">c</code> una variabile int.

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

Isalnum restituisce </code style="color : green">1</code> se c è un </code style="color : green">alphanumeric character</code> o </code style="color : green">0</code> se non è ne una </code style="color : green">lettera dell'alphabeto ne una cifra</code>.

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

Nella nostra funzione prendiamo il parametro e lo passiamo alle funzioni </code style="color : green">ft_isalpha</code> e </code style="color : green">ft_isdigit</code>. Se la chiamata va a buon fine ritorniamo </code style="color : green">1</code>, altrimenti ritorniamo </code style="color : green">0</code>.

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtIsalpha}$$

### $${\color{lightblue}Descrizione}$$

Funzione che nel linguaggio C si trova nella libreria <ctype.h>. Questa funzione controlla che l'argomento passato sia una lettera dell'alfabeto.

### $${\color{lightblue}Dichiarazione}$$

Essa è dicharata in questo modo:

<code style="color : green">int isalpha(int argument)</code>

La replica di questa funzione in questa libreria è dichiarata in questa maniera:

<code style="color : green">int	ft_isalpha(int c)</code>

### $${\color{lightblue}Parametri}$$

Richiede un solo argomento, </code style="color : green">c</code> una variabile int.

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

Isalpha restituisce </code style="color : green">1</code> se l'argomento passato è una </code style="color : green">lettera dell'alfabeto</code> o </code style="color : green">0</code> se non è una </code style="color : green">lettera dell'alphabeto</code>.

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

Nella nostra funzione prendiamo il parametro e controlliamo che il numero ascii sia compreso tra </code style="color : green">65(A) e 90(Z)</code> per le lettere maiuscole e tra </code style="color : green">97(a) e 122(z)</code> per le minuscole. Se è compreso in questo range ritorniamo 1, altrimenti ritorniamo 0.

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtIsascii}$$

### $${\color{lightblue}Descrizione}$$

Funzione che nel linguaggio C si trova nella libreria <ctype.h>. Questa funzione determina se un particolare carattere è un carattere ASCII.

### $${\color{lightblue}Dichiarazione}$$

Essa è dicharata in questo modo:

<code style="color : green">int isascii(int argument)</code>

La replica di questa funzione in questa libreria è dichiarata in questa maniera:

<code style="color : green">int	ft_isascii(int c)</code>

### $${\color{lightblue}Parametri}$$

Richiede un solo argomento, </code style="color : green">c</code> una variabile int.

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

Isascii restituisce </code style="color : green">1</code> se C è un </code style="color : green">ascii character</code> o </code style="color : green">0</code> se non è ne un </code style="color : green">ascii character</code>.

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

Nella nostra funzione prendiamo il parametro e controlliamo che il numero ascii sia compreso tra </code style="color : green">0(NULL) e 127(DEL)</code>.

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtIsdigit}$$

### $${\color{lightblue}Descrizione}$$

Funzione che nel linguaggio C si trova nella libreria <ctype.h>. Questa funzione controlla che l'argomento passato sia un numero.

### $${\color{lightblue}Dichiarazione}$$

Essa è dicharata in questo modo:

<code style="color : green">int isdigit(int arg)</code>

La replica di questa funzione in questa libreria è dichiarata in questa maniera:

<code style="color : green">int	ft_isdigit(int c)</code>

### $${\color{lightblue}Parametri}$$

Richiede un solo argomento, </code style="color : green">c</code> una variabile int.

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

Isalpha restituisce </code style="color : green">1</code> se l'argomento passato è una </code style="color : green">lettera dell'alfabeto</code> o </code style="color : green">0</code> se </code style="color : green">non è una lettera dell'alphabeto</code>.

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

Nella nostra funzione prendiamo il parametro e controlliamo che il numero ascii sia compreso tra </code style="color : green">48(0) e 57(9)</code>. Se è compreso in questo range ritorniamo 1, altrimenti ritorniamo 0.

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtIsprint}$$

### $${\color{lightblue}Descrizione}$$

Funzione che nel linguaggio C si trova nella libreria <ctype.h>. Questa funzione controlla che l'argomento passato sia un carattere che può essere stampato.

### $${\color{lightblue}Dichiarazione}$$

Essa è dicharata in questo modo:

<code style="color : green">int isprint(int arg)</code>

La replica di questa funzione in questa libreria è dichiarata in questa maniera:

<code style="color : green">int	ft_isprint(int c)</code>

### $${\color{lightblue}Parametri}$$

Richiede un solo argomento, </code style="color : green">c</code> una variabile int.

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

Isalpha restituisce </code style="color : green">1</code> se l'argomento passato è un </code style="color : green">carattere stampabile</code> o </code style="color : green">0</code> se </code style="color : green">non è un carattere stampabile</code>.

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

Nella nostra funzione prendiamo il parametro e controlliamo che il numero ascii sia compreso tra </code style="color : green">32(' ') e 126(~)</code>. Se è compreso in questo range ritorniamo 1, altrimenti ritorniamo 0.

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtItoa}$$

### $${\color{lightblue}Descrizione}$$

Funzione che nel linguaggio C si trova nella libreria <stdlib.h>. Questa funzione converte il numero di input nella stringa C corrispondente utilizzando la base specificata.

### $${\color{lightblue}Dichiarazione}$$

Essa è dicharata in questo modo:

<code style="color : green">char* itoa(int value, char* buffer, int base)</code>

La replica di questa funzione in questa libreria è dichiarata in questa maniera:

<code style="color : green">char	*ft_itoa(int n)</code>

### $${\color{lightblue}Parametri}$$

Richiede un solo argomento, </code style="color : green">n</code> una variabile int.

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

Itoa restituisce un puntatore alla stringa con terminazione null risultante, come il buffer dei parametri.

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

La nostra funzione prende il parametro passato e lo trasforma da in un </code style="color : green">long,</code> calcola la </code style="color : green">lughezza</code> del parametro passato, e infine </code style="color : green">alloca memoria per una stringa</code> dove salveremo il </code style="color : green">risultato finale.</code>

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtLstaddBack}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtLstaddFront}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtLstclear}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtLstdelone}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtLstiter}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtLstlast}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtLstmap}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtLstnew}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtLstsize}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtMemchr}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtMemcmp}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtMemcpy}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtMemmove}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtMemset}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtPutcharFd}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtPutendlFd}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtPutnbrFd}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtPutstrFd}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}Ftsplit}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtStrchr}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtStrdup}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtStriteri}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtStrjoin}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtStrlcat}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtStrlcpy}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtStrlen}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtStrmapi}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtStrncmp}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtStrnstr}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtStrrchr}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtStrtrim}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtSubstr}$$

### $${\color{lightblue}Descrizione}$$

### $${\color{lightblue}Dichiarazione}$$

### $${\color{lightblue}Parametri}$$

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtTolower}$$

### $${\color{lightblue}Descrizione}$$

Funzione che nel linguaggio C si trova nella libreria <ctype.h>. Quesat funzione controlla che il carattere passato sia una lettera maiscuola, in caso sia vero la trasforma in minuscola.

### $${\color{lightblue}Dichiarazione}$$

Essa è dicharata in questo modo:

<code style="color : green">int tolower(int argument)</code>

La replica di questa funzione in questa libreria è dichiarata in questa maniera:

<code style="color : green">int	ft_tolower(int c)</code>

### $${\color{lightblue}Parametri}$$

Richiede un solo argomento, </code style="color : green">c</code> una variabile int.

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

Tolower ritorna l'argomento passato.

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

La nostra funzione prende l'argomento passato e ontrolla che sia un </code style="color : green">carattere maiuscolo</code>, in caso sia vero aggiunge il valore </code style="color : green">32</code> in modo che in </code style="color : green">numero ascii</code> risulti la stessa lettera ma </code style="color : green">minuscola</code>.

-------------------------------------------------------------------------------------------------------------------------------------

## $${\color{cyan}FtToupper}$$

### $${\color{lightblue}Descrizione}$$

Funzione che nel linguaggio C si trova nella libreria <ctype.h>. Quesat funzione controlla che il carattere passato sia una lettera miniscola, in caso sia vero la trasforma in maiuscola.

### $${\color{lightblue}Dichiarazione}$$

Essa è dicharata in questo modo:

<code style="color : green">int toupper(int argument)</code>

La replica di questa funzione in questa libreria è dichiarata in questa maniera:

<code style="color : green">int	ft_toupper(int c)</code>

### $${\color{lightblue}Parametri}$$

Richiede un solo argomento, </code style="color : green">c</code> una variabile int.

### $${\color{lightblue}Valore \space \color{lightblue}di \space \color{lightblue}ritorno}$$

Toupper ritorna l'argomento passato.

### $${\color{lightblue}Analisi \space \color{lightblue}funzione}$$

La nostra funzione prende l'argomento passato e ontrolla che sia un </code style="color : green">carattere minuscolo</code>, in caso sia vero sottrae il valore </code style="color : green">32</code> in modo che in </code style="color : green">numero ascii</code> risulti la stessa lettera ma </code style="color : green">maiuscola</code>.

-------------------------------------------------------------------------------------------------------------------------------------
