---
title: ✏️ Hands on - DataFrames columns missing difficult
slug: hands-on-dataframes-columns-missing-difficult
abstract: It's time to put everything you've learned into practice. Try to correctly complete this code!
---

# Ciclo for

Immagina che la lista della spesa è stata scritta dal tuo cuginetto che va in seconda elementare. Le lettere sono state scritte randomicamente un po' maiuscole e un po' minuscole. Inoltre immagina che tu sia di frettissima e non sia riuscito a leggerla in anticipo, quindi ti trovi al banco frigo del supermercato, e l'unica cosa che ti interessa sapere a questo punto è: c'è il mascarpone nella lista della spesa?

```python
lista_spesa = ["SavOIArdi", "maScaRpOne", "caFFè", "cAcAO"]

#usa un ciclo for per indagare ogni ingrediente della lista_spesa
___ ingrediente in ___:

    #non sapendo come il tuo cuginetto ha scritto mascarpone, forse ti conviene trasformare ogni ingrediente in minuscolo, no?
    ___ ingrediente.___ == "mascarpone":
        print("Sì, nella lista della spesa c'è il mascarpone")
    else:
        print("No, niente mascarpone")

#digita l'output:
No, niente mascarpone
___ 
No, niente mascarpone
____
```

# Statement if

beh scritto così, il comando di prima non è utilissimo... per ben 3 volte ti ha detto che il mascarpone non era nella lista perché l'ingrediente preso in considerazione non era il mascarpone... proviamo a creare una lista vuota che andremo a riempire solo se il mascarpone è presente!

```python
lista_spesa = ["SavOIArdi", "maScaRpOne", "caFFè", "cAcAO"]
lista_mascarpone = ___

for ingrediente ___ ___:
    if ingrediente.lower() ___ ____:
        lista_mascarpone.___(___)
    else:
        pass

print(lista_mascarpone)
```

Trovi le soluzioni nel prossimo capitolo!