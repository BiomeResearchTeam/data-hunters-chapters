---
title: 🪄 Solution - DataFrames columns missing 2
slug: solution-dataframes-columns-missing-2
abstract: Did you successfully complete the code?
---

Daje, dopo questo step è tutta in discesa!

POV: sei un partecipante del workshop Data Hunters e vuoi curare i metadati del progetto ERP131433. Nel primo esercizio, verifica la correttezza del valore contenuto nella colonna onnipresente. Nel secondo esercizio,verifica la presenza di una delle 7 colonne non sempre presenti, ed eventualmente la correttezza dell'informazione contenuta!


# ESERCIZIO 1

```python
import pandas as pd

df = pd.read_csv("ERP131433_df.tsv", sep="\t")

#verifica la correttezza dell'informazione contenuta nella colonna "instrument_model"
modello = df["instrument_model"].unique()
print(modello)

#non è corretto
["VALORE SBAGLIATO"]

#crea una nuova colonna con l'informazione corretta
df["SKIOME_instrument_model"] = "Illumina MiSeq"
```

# ESERCIZIO 2

```python
import pandas as pd

df = pd.read_csv("ERP131433_df.tsv", sep="\t")

colonne = df.columns.to_list()
colonne_trovate = []

#cerca il valore Italy per capire se esiste una colonna "individuals_nationality"
for colonna in colonne:
    if "Italy".lower() in colonna.lower():
        colonne_trovate.append(colonna)
    else:
        pass

if len(colonne_trovate)>0:
    for colonna in colonne_trovate:
        print(colonna, df[colonna].unique())
else:
    print("nessuna colonna trovata!")

#supponiamo che non è stata trovata nessuna colonna contente "Italy": 
#crea la colonna "SKIOME_individuals_nationality"
df["SKIOME_individuals_nationality"] = "Italy"
```

Se hai dubbi scrivimi! [sara.fumagalli@unimib.it](mailto:sara.fumagalli@unimib.it)