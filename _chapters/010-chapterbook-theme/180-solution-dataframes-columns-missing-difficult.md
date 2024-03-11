---
title: SOLUTION - DataFrames columns missing difficult
slug: solution-dataframes-columns-missing-difficult
abstract: Did you successfully complete the code?
---

# Ciclo for

Immagina che la lista della spesa è stata scritta dal tuo cuginetto che va in seconda elementare. Le lettere sono state scritte randomicamente un po' maiuscole e un po' minuscole. Inoltre immagina che tu sia di frettissima e non sia riuscito a leggerla in anticipo, quindi ti trovi al banco frigo del supermercato, e l'unica cosa che ti interessa sapere a questo punto è: c'è il mascarpone nella lista della spesa?

```python
lista_spesa = ["SavOIArdi", "maScaRpOne", "caFFè", "cAcAO"]

#usa un ciclo for per indagare ogni ingrediente della lista_spesa
for ingrediente in lista_spesa:

    #non sapendo come il tuo cuginetto ha scritto mascarpone, forse ti conviene trasformare ogni ingrediente in minuscolo, no?
    if ingrediente.lower() == "mascarpone":
        print("Sì, nella lista della spesa c'è il mascarpone")
    else:
        print("No, niente mascarpone")

#digita l'output:
No, niente mascarpone
Sì, nella lista della spesa c'è il mascarpone
No, niente mascarpone
No, niente mascarpone
```

# Statement if

beh scritto così, il comando di prima non è utilissimo... per ben 3 volte ti ha detto che il mascarpone non era nella lista perché l'ingrediente preso in considerazione non era il mascarpone... proviamo a creare una lista vuota che andremo a riempire solo se il mascarpone è presente!

```python
lista_spesa = ["SavOIArdi", "maScaRpOne", "caFFè", "cAcAO"]
lista_mascarpone = []

for ingrediente in lista_spesa:
    if ingrediente.lower() == "mascarpone":
        lista_mascarpone.append(ingrediente)
    else:
        pass

print(lista_mascarpone)
```

Se hai dubbi scrivimi! [sara.fumagalli@unimib.it](mailto:sara.fumagalli@unimib.it)