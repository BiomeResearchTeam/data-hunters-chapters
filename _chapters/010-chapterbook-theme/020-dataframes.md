---
title: DataFrames
slug: dataframes
abstract: Uh, using a dataframe as tabular metadata? Then why not use Excel?
---

# I nostri metadati come DataFrame

{% include figure.html
    caption="Credits: https://www.geeksforgeeks.org/python-pandas-dataframe/"
    url="/assets/demo/1.1-df.png"
%}

Un DataFrame rappresenta una tabella bidimensionale costituita da righe e colonne, simile a un foglio di calcolo Excel. Il DataFrame è uno dei vari tipi di variabile che potrai trovare in Python! In questo workshop, il DataFrame costituisce la variabile principale: infatti nei progetti che affronteremo, i metadati da curare saranno trattati come DataFrame. Quindi, gran parte del nostro lavoro consisterà nella manipolazione e nell'analisi dei metadati strutturati in DataFrame.

---


# Importare il file di metadati come DataFrame

Per prima cosa dobbiamo leggere il file di metadati come un DataFrame:

```python
import pandas as pd

df = pd.read_csv("ERP020892_df.tsv", sep="\t")
print(df)
```

{% include figure.html
    url="/assets/demo/1.1-print_df.png"
%}

Ecco, abbiamo iniziato importando la libreria Pandas per poter sfruttare le sue funzioni. La prima funzione che abbiamo esplorato è `read_csv`, essenziale per leggere un file tabulare (csv, tsv, ecc.) e convertirlo in un DataFrame. In questa funzione, abbiamo indicato il nome del file tra virgolette (perché è una stringa, un altro tipo di variabile in Python!) e il separatore del file. Nel nostro caso, i metadati sono in formato TSV (Tab-Separated Values), cioè i dati sono separati da un tab. Per questo motivo, nella funzione dobbiamo aggiungere dopo il nome del file, l'opzione `sep="\t"` per indicare alla funzione che i dati sono separati da tabulazione.

Ah, nota che abbiamo usato una funzione predefinita di Python: `print()`. Questa funzione è utilizzata per visualizzare ciò che viene inserito tra le sue parentesi. In questa caso gli abbiamo chiesto di mostrarci il DataFrame df.

---

# Let's code!
    
