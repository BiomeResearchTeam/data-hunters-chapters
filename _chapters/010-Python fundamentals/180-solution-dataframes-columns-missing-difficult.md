---
title: 🪄 Solution - DataFrames columns missing difficult
slug: solution-dataframes-columns-missing-difficult
abstract: Did you successfully complete the code?
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
lista_colonne = df.columns.to_list()
print(lista_colonne)
```
```out
["dolce", "ingrediente"]
```

Ora creaiamo una lista vuota, che verrà riempita con la colonna che contiene la parola mascarpone... sempre che la parola mascarpone sia presente!

```python
colonna_mascarpone = []

#ora usiamo un ciclo for per prendere in considerazione una colonna per volta 
#per esempio prima sarà la colonna "dolce" e poi la colonna "ingrediente"
for colonna in lista_colonne:

    #usiamo la condizione if per cercare se la parola mascarpone è presente nella colonna presa in considerazione ALMENO UNA volta    
    if (df[colonna] == "mascarpone").any():
        colonne_trovate.a___(colonna)
    else:
        pass

print(colonna_mascarpone)
```
```out
ingrediente
```

Se hai dubbi scrivimi! [sara.fumagalli@unimib.it](mailto:sara.fumagalli@unimib.it)