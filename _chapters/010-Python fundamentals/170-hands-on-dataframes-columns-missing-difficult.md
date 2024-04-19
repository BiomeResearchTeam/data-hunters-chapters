---
title: ✏️ Hands on - DataFrames columns missing difficult
slug: hands-on-dataframes-columns-missing-difficult
abstract: It's time to put everything you've learned into practice. Try to correctly complete this code!
---

A questo punto aggiungiamo i nuovi metodi imparati (`.any()` e `.append()`) al `for` e all'`if`, prima di ritornare a curare i nostri metadati.

Lavoriamo ora con il dataframe `df`, che vedi qui di seguito.

<div class="table-wrapper" markdown="block">

| dolce | ingrediente |
|:------:|:------:|
| tiramisù  | mascarpone |
| crostata | marmellata |
| budino | cioccolato |
| millefoglie | CREMA |

Per esempio in questo dataframe c'è la parola "mascarpone"? Se sì, in quale colonna si trova?

```python
#iniziamo con il recuperare la lista delle colonne
lista_colonne = df.___.to_list()
print(___)
```
```out
["dolce", "ingrediente"]
```

Ora creaiamo una lista vuota, che verrà riempita con la colonna che contiene la parola mascarpone... sempre che la parola mascarpone sia presente!

```python
colonna_mascarpone = ___

#ora usiamo un ciclo for per prendere in considerazione una colonna per volta 
#per esempio prima sarà la colonna "dolce" e poi la colonna "ingrediente"
for colonna in ___:

    #usiamo la condizione if per cercare la parola nella colonna presa in considerazione 
    if (df[___] == "mascarpone").___():
        colonne_trovate.a___(colonna)
    else:
        pass

print(colonna_mascarpone)
```
```out
ingrediente
```

Trovi le soluzioni nel prossimo capitolo!