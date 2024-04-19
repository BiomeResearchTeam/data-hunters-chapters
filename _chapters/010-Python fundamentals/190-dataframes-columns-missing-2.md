---
title: 📖 DataFrames columns missing 2
slug: dataframes-columns-missing-2
abstract: How to check if a column is present in the dataframe? And how do we check if the dataframe value matches the one in the paper?
---

# Let's manipulate the Dataframe: COLONNE NON SEMPRE PRESENTI

Quindi ritorniamo a dove eravamo rimasti nella cura del nostro progetto ERP020892.
Attualmente ci troviamo nella fase di cura delle 6 colonne che potrebbero non essere presenti. Ti ricordo che innanzitutto dobbiamo cercare se queste colonne sono presenti! Se una colonna è presente, procediamo con la verifica dell'informazione contenuta, assicurandoci che coincida con quanto abbiamo trovato nel paper che abbiamo letto. Se la colonna è assente, allora dobbiamo crearla.

Supponiamo di voler cercare se nel nostro DataFrame df esiste una colonna "body_site" che contenga l'informazione "Hands", cioè il sito di campionamento del microbioma (questa informazione è inventata per l'esempio).

```python
#riscriviamo i passaggi già visti in precedenza:
colonne = df.columns.to_list()

colonne_trovate = []

for colonna in colonne:
    if (df[colonna] == "Hands").any():
        colonne_trovate.append(colonna)
    else:
        pass
#a questo punto possiamo misurare la lunghezza della lista colonne_trovate: se la lunghezza è 
#maggiore di 0 significa che è stata trovata almeno una colonna che contiene l'informazione 
#che stiamo cercando!

#per calcolare la lunghezza di una lista usiamo la funzione len()
if len(colonne_trovate)>0:

    #questo blocco di codice viene fatto correre solo se la condizione dell'if è vera, cioè
    #se la lunghezza della lista colonna trovate è maggiore di 0.
    #quindi ora possiamo iterare tra le colonne trovate e visualizzare quali valori unici 
    #contiene. Questa fase è cruciale per comprendere se l'informazione ricercata, come 
    #ad esempio "Hands", è contenuta in una colonna dedicata al body_site oppure se è 
    #mescolata con altre informazioni. In quest'ultimo caso dovremo noi creare la colonna 
    #specifica per il body_site che ti ricordo essere "SKIOME_body_site"
    for colonna in colonne_trovate:
        print(colonna, df[colonna].unique())
else:
    print("nessuna colonna trovata!")

```

```out
nessuna colonna trovata!
```

Non è stata trovata nessuna colonna che contenesse l'informazione del body_site, e quindi creiamo la colonna nuova!

```python
df["SKIOME_body_site"] = "hands"
```

Ecco la parte più complicata del workshop: verificare se le 6 colonne siano presenti nei metadati, e se l'informazione che contengono sia giusta. Ti faccio notare che in questa slide hai scoperto l'ultima fondamentale per il workshop: `len()`. `len()` è una funzione built-in, che restituisce la lunghezza di un oggetto, come nel nostro caso una lista. 

Cosa abbiamo fatto in questa slide? Abbiamo controllato se la lista `colonne_trovate` contenesse almeno un elemento, cioè almeno il nome di una colonna. Se la lista ha una lunghezza maggiore di 0, allora per ogni `colonna` presente in `colonne_trovate` avrebbe stampato il nome della `colonna` e i valori unici contenuti in quella `colonna`. Avremmo quindi potuto così determinare se esistesse una colonna specifica per il "body_site". (Ah, ti ricordo che se esiste una colonna specifica per il "body_site" e il valore contenuto è corretto, non devi intervenire! Se invece la colonna esiste ma il valore è scorretto, devi creare una nuova colonna con il contenuto corretto). Se invece, come nel nostro caso, la lista `colonne_trovate` è vuota, allora viene eseguito il comando dopo `else:`: stampa la frase "nessuna colonna trovata!". A questo punto non ti resta che creare una nuova colonna contenente quell'informazione.

⚠️⚠️⚠️ ATTENZIONE: in questo modo verrà trovata solo la colonna che contiene esattamente la parola "Hands". Anche una singola lettera maiuscola non avrebbe fatto trovare la colonna... Come fare per trovare la parola indipendentemente da maiuscole e minuscole?

---

# Let's manipulate the Dataframe: CERCARE IL VALORE CASE-INSENSITIVE

Altro esempio. Supponiamo di cercare se esiste la colonna "target_region", cercando il valore "V3-V4" che abbiamo trovato nel paper (questa informazione è inventata per l'esempio).

```python
import re

colonne = df.columns.tolist()
colonne_trovate = []

pattern = re.compile(r"V3-V4", flags=re.IGNORECASE)

for colonna in colonne:
    if df[colonna].astype(str).str.contains(pattern).any():
        colonne_trovate.append(colonna)
    else:
        pass

if len(colonne_trovate)>0:
    for colonna in colonne_trovate:
        print(colonna, df[colonna].unique())
else:
    print("nessuna colonna trovata!")
```

```out
sample_alias, skin microbiome sample v3-v4 Italy
run_title, A Comprehensive Study on the Facial Microbial Landscape with a Focus on the V3-V4 Region in Italian Elderly
```

Innanzitutto ti faccio notare che abbiamo bisogno di una nuova libreria `import re`, e che adesso dobbiamo inserire il valore che vogliamo cercare qui: `pattern = re.compile(r"VALORE CHE VOGLIAMO CERCARE", flags=re.IGNORECASE)`. Grazie all'opzione `flags=re.IGNORECASE`, ora possiamo cercare il valore senza preoccuparci se scritto in maiuscolo o minuscolo, e inoltre troverà anche colonne in cui non c'è solo scritto quel valore.

Guarda: in questo caso la lista `colonne_trovate` è maggiore di 0, e quindi ha stampato il nome della colonna e i valori unici contenuti. In questo caso, ha stampato prima la colonna `sample_alias` che contiene `skin microbiome sample v3-v4 Italy`, e poi la colonna `run_title` con il valore unico `A Comprehensive Study on the Facial Microbial Landscape with a Focus on the V3-V4 Region in Italian Elderly`. Come puoi vedere, non è stata trovata nessuna colonna specifica che contenga **solo** l'informazione della target_region, e quindi creiamo la colonna nuova! 

```python
df["SKIOME_target_region"] = "V3-V4"
```

In questo caso abbiamo cercato se esistesse un'altra delle 6 colonne: target_region. Quindi abbiamo creato la lista `colonne_trovate` che contiene il nome delle colonne in cui il valore "V3-V4" è stato trovato. Quando abbiamo eseguito il comando `if len(colonne_trovate)>0`, la condizione era vera e quindi è stato eseguito il comando:
`for colonna in colonne_trovate:
    print(colonna, df[colonna].unique())`

Come puoi osservare, l'output fornisce il nome della colonna in cui è stato individuato "V3-V4" e il valore unico presente in quella colonna. In entrambe le colonne, puoi notare che il valore "V3-V4" è mescolato con altre informazioni, da cui possiamo dedurre l'assenza di una colonna specifica denominata "target_region". Perfetto! Allora dobbiamo crearla!


# Let's code!