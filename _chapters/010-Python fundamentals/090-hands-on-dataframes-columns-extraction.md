---
title: HANDS ON - DataFrames columns extraction
slug: hands-on-dataframes-columns-extraction
abstract: It's time to put everything you've learned into practice. Try to correctly complete this code!
---

Ottimo, ti va di mettere in pratica quello che hai imparato?

POV: sei un partecipante del workshop Data Hunters e vuoi curare i metadati del progetto ERP131433. Seleziona la colonna "DOI" e visualizza i suoi valori unici!


```python
import ___ as ___

df = pd.read_csv("ERP131433_df.tsv", sep="\t")

#verifica che ci sia la colonna DOI nel tuo df, unisci nello stesso comando i due metodi che conosci!
lista_colonne = df.___.___()
print(___)

#estrai la colonna DOI e seleziona i suoi valori unici
colonna_doi_unici = df[___].___()
print(colonna_doi_unici)
```


Trovi la soluzione nel prossimo capitolo!