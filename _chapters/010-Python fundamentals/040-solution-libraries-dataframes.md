---
title: SOLUTION - Libraries & DataFrames
slug: solution-libraries-dataframes
abstract: Did you successfully complete the code?
---

È tempo di mettere le mani in pasta, cioè in Python!
POV: sei un partecipante del workshop Data Hunters e vuoi curare i metadati del progetto ERP131433. Il primo passaggio che devi fare è leggere il file ERP131433_df.tsv come DataFrame.


```python
import pandas as pd

df = pd.read_csv("ERP131433_df.tsv", sep="\t")
print(df)
```

TA-DAAN: hai scritto il tuo primo codice ✨

Se hai dubbi scrivimi! [sara.fumagalli@unimib.it](mailto:sara.fumagalli@unimib.it)