---
title: 🪄 Solution - DataFrames columns
slug: solution-dataframes-columns
abstract: Did you successfully complete the code?
---

È tempo di mettere in pratica quanto imparato!

POV: sei un partecipante del workshop Data Hunters e vuoi curare i metadati del progetto ERP131433. Ricordati di importare Pandas, leggere il dataframe, e prova a vedere da quali colonne è formato!


```python
import pandas as pd 

df = pd.read_csv("ERP131433_df.tsv", sep = "\t")

colonne = df.columns
lista_colonne = colonne.to_list()
print(lista_colonne)
```

Se hai dubbi scrivimi! [sara.fumagalli@unimib.it](mailto:sara.fumagalli@unimib.it)