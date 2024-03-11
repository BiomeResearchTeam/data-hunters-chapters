---
title: 🪄 Solution - Saving DataFrame
slug: solution-saving-df
abstract: Did you successfully complete the code?
---

Vedo già il traguardo, siamo alle battute finali!

POV: sei un partecipante del workshop Data Hunters e vuoi curare i metadati del progetto ERP131433. Hai finito di curare questo progetto! Non ti resta che salvare il file come SKIOME_ERP131433_df.tsv


```python
#per questa ultima volta ti abbuono tutti i passaggi precedenti...
#supponiamo di avere curato le 9 colonne del DataFrame df e ora vogliamo salvarlo con il nome "SKIOME_ERP131433_df.tsv"

df.to_csv("SKIOME_ERP131433_df.tsv", sep = "\t", index=False)
```

Se hai dubbi scrivimi! [sara.fumagalli@unimib.it](mailto:sara.fumagalli@unimib.it)