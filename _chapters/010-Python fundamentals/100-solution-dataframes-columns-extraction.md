---
title: 🪄 Solution - DataFrames columns extraction
slug: solution-dataframes-columns-extraction
abstract: Did you successfully complete the code?
---

Ottimo, ti va di mettere in pratica quello che hai imparato?

POV: sei un partecipante del workshop Data Hunters e vuoi curare i metadati del progetto ERP131433. Seleziona la colonna "DOI" e visualizza i suoi valori unici!


```python
import pandas as pd

df = pd.read_csv("ERP131433_df.tsv", sep="\t")

#verifica che ci sia la colonna DOI nel tuo df, unisci nello stesso comando i due metodi che conosci!
lista_colonne = df.columns.to_list()
print(lista_colonne)

#estrai la colonna DOI e seleziona i suoi valori unici
colonna_doi_unici = df["DOI"].unique()
print(colonna_doi_unici)
```

Se hai dubbi scrivimi! [sara.fumagalli@unimib.it](mailto:sara.fumagalli@unimib.it)