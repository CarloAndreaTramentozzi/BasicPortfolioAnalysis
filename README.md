# 📊 Basic Portfolio Analysis

Questo progetto mostra come effettuare una **semplice analisi di portafoglio** utilizzando dati storici scaricati da Yahoo Finance.  
L’obiettivo è capire:
- come calcolare i rendimenti dei titoli,
- come analizzare l’andamento cumulato di un investimento,
- come valutare le correlazioni tra asset.

---

## 📖 Struttura del notebook

### 1️⃣ Importazione librerie
```python
import yfinance as yf
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

```
In questa fasi importiamo yfinance per dati finanziari storici direttamente da Yahoo Finance, per manipolazione ed elaborazione dati importo pandas e numpy mentre pe rla rappresentyazione e la vsualizzazione utilizziamo matplotlib e seasborn .



### 2️⃣ Download dei dati storici

```

tickers = ["AAPL", "MSFT", "GOOG", ...]
data = yf.download(tickers, start="YYYY-MM-DD", end="YYYY-MM-DD")["Adj Close"]

```


### 3️⃣ Calcolo dei rendimenti

I rendimenti giornalieri si ottengono come variazione percentuale dei prezzi e Rimuoviamo i valori mancanti con .dropna().



### 4️⃣ Rendimenti cumulati

Calcoliamo il rendimento cumulato di un investimento ipotizzando di reinvestire ogni giorno.

Visualizziamo l’andamento per capire quale asset è cresciuto di più nel tempo.


### 5️⃣ Analisi delle correlazioni


```

plt.figure(figsize=(8,6))
sns.heatmap(returns.corr(), annot=True, cmap="coolwarm")


```

Creiamo una matrice di correlazione dei rendimenti, usiamo una heatmap per evidenziare i legami tra i vari titoli, che indicherà il rischio effettivo , considerate le corelazioni nascoste.
Le correlazioni ci dicono se due asset tendono a muoversi insieme (correlazione positiva) o in direzioni opposte (correlazione negativa).
Questo è fondamentale per la diversificazione del portafoglio.



##📜 Considerazioni 

Al termine dell’analisi otteniamo i grafici dei rendimenti cumulati per ciascun titolo e una heatmap delle correlazioni tra asset, un quadro di insieme utile per valutare performance e diversificazione.




























