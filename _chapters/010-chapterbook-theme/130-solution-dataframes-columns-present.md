---
title: SOLUTION - DataFrames columns present
slug: solution-dataframes-columns-present
abstract: Did you successfully complete the code?
---

Eccoci: è la tua opportunità di testare tutto quello che hai imparato!

POV: sei un partecipante del workshop Data Hunters e vuoi curare i metadati del progetto ERP131433. Estrai il valore unico della colonna "library_strategy" e crea una nuova colonna con il valore corretto.


```python
#importa pandas e leggi il file come DataFrame
import pandas as pd
df = pd.read_csv("ERP131433_df.tsv", sep="\t")

#estrai il valore unico della colonna library_strategy e stampala
#il valore contenuto è sbagliato
strategia = df["library_strategy"].unique()
print(strategia)
["VALORE SBAGLIATO"]

#crea una nuova colonna chiamata "SKIOME_library_strategy" con il valore corretto
df["SKIOME_library_strategy"] = "AMPLICON"
```

Se hai dubbi scrivimi! [sara.fumagalli@unimib.it](mailto:sara.fumagalli@unimib.it)