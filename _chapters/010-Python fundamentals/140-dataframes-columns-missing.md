---
title: 📖 DataFrames columns missing
slug: dataframes-columns-missing
abstract: How to check if a column is present in the dataframe? Using a for loop and an if statement.
---

# Let's manipulate the Dataframe: COLONNE NON SEMPRE PRESENTI

OK passiamo alle altre 6 colonne che potrebbero non esserci. Iniziamo a cercarle! Per farlo useremo nuove strutture di Python, ma niente paura: ti spieghiamo tutto!

Supponiamo di voler cercare se nel nostro DataFrame `df` esiste una colonna che contiene l'informazione "Hands", cioè il sito di campionamento del microbioma. Ma da dove arriva il valore "Hands"? L'abbiamo trovato nel paper! In pratica: per capire se esiste una colonna (in questo caso quella sul sito di campionamento) cerchiamo il valore indicato nel paper. Infatti il ragionamento che facciamo è il seguente: se dovesse esistere una colonna specifica sul sito di campionamento allora deve contenere il valore che è stato indicato nel paper.

```python
#iniziamo con qualcosa che conosciamo già: creiamo una lista delle colonne del nostra DataFrame 
colonne = df.columns.to_list()

#NOVITÀ: creiamo una lista vuota che compileremo man mano
colonne_trovate = []

#NOVITÀ: CICLO FOR e CONDIZIONE IF
for colonna in colonne:
    if (df[colonna] == "Hands").any():
        colonne_trovate.append(colonna)
    else:
        pass
```

MMH con calma: cosa abbiamo visto a sinistra? Andiamo in ordine:
* Abbiamo creato una lista contenente i nomi delle colonne del nostro DataFrame df
* Abbiamo creato una lista vuota, perché intendiamo popolarla con i nomi delle colonne in cui troviamo il valore "Hands"
* Abbiamo utilizzato un ciclo `for` per considerare una colonna alla volta presente nella lista `colonne`
* Per ogni colonna abbiamo verificato con l'istruzione `if` se il termine "Hands" fosse presente in quella colonna. In particolare abbiamo cercato se fosse presente almeno una volta grazie al methodo `.any()`
* Se il valore "hands" è presente nella colonna, abbiamo usato il metodo `.append()` per appendere la `colonna` nella lista di `colonne_trovate`.
* Se il valore "hands" non è presente nella colonna, ndicato di passare alla prossima colonna senza aggiungere quella `colonna` alla lista `colonne_trovate`.

Nelle prossime slides ti spieghiamo meglio il funzionamento di `for` e `if`

---

# `for` LOOP

Il loop `for` è una struttura molto utilizzate in Python. Questo loop consente di iterare in una serie di diversi elementi, come, nel nostro caso, gli elementi di una lista. Per capire il funzionamento di un ciclo `for` possiamo stampare l'elemento che viene preso in considerazione, così:


```python
lista_parole = ["data", "hunters", "rock", "!"]
for parola in lista_parole:
    print(parola)
```

```out
data
hunters
rock
!
```

Come hai visto, il ciclo `for` ha preso in considerazione un elemento (`parola`) alla volta dalla lista fornita (`lista_parole`), e ha eseguito il comando specificato dopo i due punti `:`, con l'indentazione corretta. In questo caso, il comando che gli abbiamo assegnato è stato quello di stampare la `parola` che stava considerando (`print(parola)`). Quindi:

* *Step 1*. `parola` = `'data'`
* *Step 2*. `parola` = `'hunters'`
* *Step 3*. `parola` = `'rock'`
* *Step 4*. `parola` = `'!'`
* Finché non ci sono più elementi nella lista e quindi il loop è finito.

Tuttavia, dopo i due punti è possibile assegnargli qualsiasi altro comando!

Ad esempio, per curare i nostri metadati, gli abbiamo chiesto di verificare una condizione per ciascun elemento che stava considerando... (Cambia slide!)

---

# `if` STATEMENT

L'istruzione `if` viene utilizzata per decidere se eseguire o meno determinati comandi. Quando si utilizza l'istruzione `if`, si valuta una condizione, ad esempio `if 5 > 4`,  la quale può essere o vera o falsa. Se la condizione è vera, viene eseguito un blocco di comandi indentati sotto l'istruzione `if`. Se la condizione è falsa, viene eseguito un altro blocco di comandi che si trova dopo `else:`.

Lo schema generale è il seguente:

```python
if condizione is True:
    fai qualcosa
else:
    fai qualcosa di diverso
```

Per esempio:
```python
if 5 > 4:
    print("La matematica non è un'opinione!")
else:
    print("Wow, le leggi della fisica sono ormai ribaltate. Nulla ha più senso")
```
```out
La matematica non è un'opinione!
```

Guarda l'esempio a lato: abbiamo richiesto di verificare la condizione "5 > 4", cioè se 5 è maggiore di 4. Dal momento che questa condizione è vera, viene eseguito il blocco di comandi che si trova intendentato dopo l'`if`, cioè `print("La matematica non è un'opinione!")`. Solo nel caso in cui la condizione fosse stata falsa, sarebbe stato eseguito il comando sotto l'istruzione `else:`.

---

# Let's code
