---
title: 📖 Libraries
slug: libraries
abstract: Introduction to Python libraries. Do they really contain books?
---

# Librerie

Quando pensiamo alle librerie, ci vengono in mente scaffali pieni di libri pieni di nozioni che abbiamo già letto o che sono lì ad aspettare che li leggeremo (... scusaci Guerra e Pace). E in effetti anche le librerie di Python possono essere pensate così: sono scaffali di codici precompilati, documentazione, classi, valori, e molto altro, che possiamo usare per svolgere delle operazioni.

---


# TGIL

{% include figure.html
    caption="Credits: https://www.interviewbit.com/blog/python-libraries/"
    url="/assets/demo/0.1-libraries.png"
%}

Thank God Is a Library: eh meno male che esistono le librerie! Come detto, le librerie contengono pacchetti di codice già scritto e che eseguono varie operazioni, evitandoci di riscrivere da zero ogni volta! Insomma, un ottimo affare.

---

# Una varietà di librerie tra cui scegliere

{% include figure.html
    caption="Credits: https://medium.com/@cyber-news/python-libraries-for-data-science-your-essential-toolbox-c21e7d7826ba"
    url="/assets/demo/0.3-libraries-examples.png"
%}

Python dispone della cosiddetta Python Standard Library che includde una serie di moduli predefiniti che vengono forniti con ogni installazione di Python. Tuttavia oltre a questa, c'è un'enorme varietà di altre librerie che possono essere scaricate! Nota che di solito una libreria è specifica per un certo argomento.

---


# PANDAS

{% include figure.html
    caption="Credits: https://realpython.com/pandas-dataframe/"
    url="/assets/demo/0.4-pandas.png"
%}


Per questo workshop la libreria che utilizzeremo è **Pandas**. Pandas è una libreria open-sorce, facile e flessibile, ampiamente utilizzata dai data scientist per la manipolazione e l'analisi dei dati. 
[Website](https://pandas.pydata.org/) || [Documentation](https://pandas.pydata.org/pandas-docs/)

Per utilizzare una qualisasi libreria, e quindi anche Pandas, è necessario richiamarla prima del suo utilizzo, garantendo così la sua disponibilità nel nostro ambiente di lavoro. 
In particolare, si fa così: `import pandas`. 
Per abbreviare il nome della libreria, è possibile usare il suo diminutivo "pd", così: `import pandas as pd`.

---


# Le funzioni di Pandas
`import pandas as pd`
`df = pd.read_csv("metadata.csv")`

Una volta importata la libreria, è sufficiente inserire il suo nome prima di una funzione affinché l'operazione di quella funzione venga eseguita. Nell'esempio qui accanto, vediamo come abbiamo prima richiamato la libreria Pandas con l'alias "pd" e successivamente utilizzato la sua funzione "read_csv" per leggere un file CSV tabulare (di cui parleremo più avanti!). Abbiamo semplicemente inserito il nome della libreria "pd" seguito dal nome della funzione, separati da un punto. In questo modo, siamo riusciti a leggere il file "metadata.csv" come un dataframe.

Niente paura, ti raccontiamo meglio di cosa si tratta nel prossimo sottocapitolo!
    
