---
title: ✏️ Hands on - DataFrames columns missing 2
slug: hands-on-dataframes-columns-missing-2
abstract: It's time to put everything you've learned into practice. Try to correctly complete this code!
---

Daje, dopo questo step è tutta in discesa!

POV: sei un partecipante del workshop Data Hunters e vuoi curare i metadati del progetto ERP131433. Nel primo esercizio, verifica la correttezza del valore contenuto in una delle colonne sempre presenti. Nel secondo esercizio, verifica la presenza di una delle 6 colonne non sempre presenti, ed eventualmente la correttezza dell'informazione contenuta!

# ESERCIZIO 1

```python
import pandas ___ ___

df = ___.___("ERP131433_df.tsv", sep="\t")

#verifica la correttezza dell'informazione contenuta nella colonna "instrument_model"
modello = ___["instrument_model"].___()
print(modello)

#non è corretto
["VALORE SBAGLIATO"]

#crea una nuova colonna "SKIOME_instrument_model" con l'informazione corretta
df___ = "Illumina MiSeq"
```

# ESERCIZIO 2

```python
import pandas as pd
import ___

df = pd.read_csv("ERP131433_df.tsv", sep="\t")

colonne = df.___.___()
colonne_trovate = ___

#cerca il valore "Italy" per capire se esiste una colonna "individuals_nationality"
pattern = ___.compile(r"Italy", flags=re.___)

for colonna in ___:
    if df[colonna].astype(str).str.contains(pattern).any():
        ___.append(___)
    else:
        pass

if ___(___)>0:
    for colonna in colonne_trovate:
        print(colonna, ___.unique())
else:
    print("nessuna colonna trovata!")

#supponiamo che non è stata trovata nessuna colonna contente "Italy": 
#crea la colonna "SKIOME_individuals_nationality"
df___ = "Italy"
```

Trovi le soluzioni nel prossimo capitolo!