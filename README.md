|Attenzione|
|----------|
|Per leggere correttamente questo documento, click destro sul file README.md e selezionare "Open Preview"|

# Array a due dimensioni
Finora abbiamo visto come un vettore rappresenta un tipo di dato strutturato che permette di aggregare dati omogenei per poterli facilmente elaborare, cioè memorizzare, ritrovare e manipolare.
Un **vettore** viene chiamato anche **array ad una dimensione** e sappiamo che è composto da elementi omogenei (tutti dello stesso tipo - intero, stringa, reale, ...) ognuno dei quali è identificato, all’interno dell’array, da un numero d’ordine detto **indice** dell’elemento.

Gli **array**, in realtà, possono avere più di una dimensione: è infatti possibile definire strutture di dati complesse, gli **array multidimensionali** (o n-dimensionali), dove a ogni dimensione vieneassociato  un  indice  e  quindi  un  elemento  viene  individuato  da  un  insieme  di  valori,  uno  per ogni dimensione.

Tra  gli  array  multidimensionali particolare  importanza  assumono  gli  **array  a  due  dimensioni**,  che prendono il nome di **matrici** (o **array bidimensionali**).

Il termine **matrice** è proprio del linguaggio matematico: si definisce matricea **n righe e m colonne**, o più brevemente **matrice di tipo (n, m)**, una tabella formata da n x m elementi, disposti su n linee orizzontali (**righe**) e m linee verticali (**colonne**).

Analogamente ai vettori, le coordinate delle matrici mantengono il nome di **indici**: il primo elemento della coppia prende il nome di **indice di riga**, il secondo di **indice di colonna**.

![image](assets/image_2.png)

| |
|-|
|**L’indice di riga (la n)** è il valore che indica la riga a cui appartiene l’elemento, cioè la sua posizione lungo la verticale, mentre **l’indice di colonna (la m)** è il valore che indica la colonna a cui appartiene l’elemento, cioè la sua posizione scorrendo la linea orizzontale: una generica cella ha quindi una coppia di **coordinate (n, m)**.|

Rappresentiamo per esempio una matrice 3 × 5 (n=3, m=5), quindi con 3 righe e 5 colonne.

![image](assets/image_3.png)

## Utilizzare le variabili di tipo matrice
Analogamente a quanto abbiamo visto per i vettori, tre sono gli elementi che caratterizzano una matrice:
- **tipo**, cioè il tipo delle celle che dovrà contenere (intero, reale, stringa, ...);
- **dimensione**, cioè il numero di righe e colonne (e quindi di celle) di cui è costituita;
- **nome**, cioè il nome univoco con cui verrà utilizzata nel programma.

## Matrici nei diagrammi di flusso
Nei diagrammi di flusso la dichiarazione di una matrice si presenta come segue:

![image](assets/image_4.png)

In questa notazione:
- il primo numero nella parentesi indica il numero di **righe n**;
- il secondo numero nella parentesi indica il numero di **colonne m**;
- il numero delle celle è dato dal prodotto n×m: in questo caso, vengono definite 15 celle (3x5).

![image](assets/image_5.png)

| |
|-|
|Come per i vettori, anche per le matrici è necessario prestare attenzione alla corretta individuazione delle celle della matrice, perché spesso ci si “dimentica” che, partendo da 0, gli estremi devono essere diminuiti di una unità quando manipoliamo dei dati.|

La cella viene individuata mediante una coppia di coordinate; per scrivere un numero nella cella di coordinate (1, 2) si utilizza:
![image](assets/image_8.png)
![image](assets/image_6.png)

per scrivere un numero nella cella di coordinate (2, 0) si utilizza
![image](assets/image_9.png)
![image](assets/image_7.png)

per scrivere un numero nella cella di coordinate (0, 2) si utilizza:

![image](assets/image_10.png)
![image](assets/image_11.png)

## Un esempio di utilizzo
Scriviamo ora il numero 7 in tutte le celle di una riga, per esempio nella seconda riga: le celle sono 5, pari al numero delle colonne, quindi è necessario effettuare 5 istruzioni di assegnamento; il risultato è il seguente:

![image](assets/image_12.png)

Per effettuare questa operazione si può sfruttare un ciclo for in quanto le dimensioni della matrice sono note a priori, cioè è noto a priori quante volte va ripetuta l'operazione di riempimento della cella:<br/>
<img src="assets/image_13.png" alt="image" width="60%"/>

Analogamente, è possibile scrivere lo stesso numero in tutti gli elementi di una  colonna, per esempio nella colonna 3:
![image](assets/image_14.png)

Usando il ciclo for:<br/>
<img src="assets/image_15.png" alt="image" width="60%"/>

## Le matrici in Java
Osserviamo come codificare le matrici in Java e riscriviamo gli esempi visti finora.
La dichiarazione di una matrice:
![image](assets/image_4.png)
Si codifica in questo modo:
```Java
...
public class Esercizio {
    public static void main(String[] args) {
        int[][] miaMatrice = new int[3][5];  
        ...
    }
}
```
Possiamo notare quindi l'analogia con la dichiarazione di un vettore:
* La matrice è caratterizzata da due dimensioni [][] anzichè una sola [],
* il tipo degli elementi contenuti nelle celle (intero),
* il nome della matrice (miaMatrice),
* la dimensione, che nel caso della matrice è composta dal numero di righe (3) ed il numero di colonne (5).

Il blocco di assegnazione, come al solito si riporta così com'è dal diagramma di flusso, quindi scriveremo:

![image](assets/image_14.png)

```Java
...
public class Esercizio {
    public static void main(String[] args) {
        int[][] miaMatrice = new int[3][5];  

        miaMatrice[0][3] = 7;
        miaMatrice[1][3] = 7;
        miaMatrice[2][3] = 7;
    }
}
```
## Esercizio 1
Nel file *Esercizio.java*, completa il contenuto della funzione *esercizio1*, riempiendo le celle della matrice come nella figura seguente. <br/>

![image](assets/image_12.png)

La matrice può essere visualizzata con l'istruzione *UtilsMatrice.visualizza(matrice);* <br/>
Eseguire il programma per controllare che il contenuto della matrice sia come ci si aspetti.

<hr/>
<details>
  <summary>Solo dopo aver svolto l'esercizio, apri qui per vedere la soluzione</summary>

```Java
public static void esercizio1() {
    int [][] miaMatrice = new int[3][5];
    miaMatrice[1][0] = 7;
    miaMatrice[1][1] = 7;
    miaMatrice[1][2] = 7;
    miaMatrice[1][3] = 7;
    miaMatrice[1][4] = 7;

    UtilsMatrice.visualizza(miaMatrice);
}
```
</details>
<hr/>

## Esercizio 2
Nel file *Esercizio.java*, completa il contenuto della funzione *esercizio2*, codificando il seguente algoritmo.<br/>
L'algoritmo risolve l'esercizio precedente, utilizzando però il ciclo for.<br/>
<img src="assets/image_13.png" alt="image" width="60%"/>
<br/>
La matrice può essere visualizzata con l'istruzione *UtilsMatrice.visualizza(matrice);* <br/>
Eseguire il programma per controllare che il risultato sia come il seguente:
```
ESERCIZIO 2: 
----- ----- -----
[0 0 0 0 0]
[7 7 7 7 7]
[0 0 0 0 0]
```

<hr/>
<details>
  <summary>Solo dopo aver svolto l'esercizio, apri qui per vedere la soluzione</summary>

```Java
public static void esercizio2() {
    int j;
    int [][] miaMatrice = new int[3][5];
    for (j=0; j<=4; j=j+1 ) {
        miaMatrice[1][j] = 7;
    }

    UtilsMatrice.visualizza(miaMatrice);
}
```
</details>
<hr/>

## Esercizio 3
Nel file *Esercizio.java*, completa il contenuto della funzione *esercizio3*, codificando il seguente algoritmo.<br/>
L'algoritmo, analogamente all'esercizio precedente, inserisce un valore nella quarta colonna utilizzando il ciclo for.<br/>
<img src="assets/image_15.png" alt="image" width="60%"/><br/>
La matrice può essere visualizzata con l'istruzione *UtilsMatrice.visualizza(matrice);* <br/>
Eseguire il programma per controllare che il risultato sia come il seguente:
```
ESERCIZIO 3: 
----- ----- -----
[0 0 0 7 0]
[0 0 0 7 0]
[0 0 0 7 0]
```
<hr/>
<details>
  <summary>Solo dopo aver svolto l'esercizio, apri qui per vedere la soluzione</summary>

```Java
void esercizio3() 
{
  int i;
  matrix<int> miaMatrice(3,5);
  for (i=0; i<=2; i=i+1 )
  {
    miaMatrice[i][3] = 7;
  }

  cout << miaMatrice;
}
```
</details>
<hr/>
