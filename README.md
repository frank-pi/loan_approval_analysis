# Loan Approval

Dieses Repository enthält ein Jupyter Notebook, das eine **Machine‑Learning‑Pipeline zur Vorhersage von Kreditzusagen** (*loan approval*) auf Basis von Bewerber‑ und Finanzdaten entwickelt.

## Inhalt

- Datenimport (CSV)
- Preprocessing & Data Cleaning  
  - Datentypen bereinigen  
  - Ausreißer (*Outliers*) behandeln (Clipping)  
  - Fehlende Werte (*NaNs*) und Duplikate behandeln  
- Explorative Datenanalyse (EDA) & Visualisierungen
- Feature Engineering
- Modellierung & Evaluation  
  - Logistic Regression (mit Skalierung)  
  - Random Forest  
  - Confusion Matrices, ROC Curve  
  - Cross‑Validation (Stratified K‑Fold)

## Datensatz

Das Notebook lädt CSV‑Dateien aus einem lokalen `data/`‑Ordner (im Original in Google Colab via Drive eingebunden).

Erwartete Dateien (siehe Notebook):
- `data/loans_modified.csv`
- `data/loans_feature.csv`

> Tipp: Falls du andere Dateinamen/Strukturen verwendest, passe im Notebook die Variable `directory` bzw. den Pfad bei `pd.read_csv(...)` an.

## Voraussetzungen

- Python 3.10+ (empfohlen)
- Jupyter / JupyterLab oder VS Code (Notebook Support)

Benötigte Python‑Pakete:
- numpy
- pandas
- matplotlib
- seaborn
- scikit-learn

Installation (Beispiel):

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -U pip
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```

## Nutzung

1. Repository klonen
2. CSV‑Dateien in `data/` ablegen
3. Notebook starten:

```bash
jupyter lab
# oder
jupyter notebook
```

4. `Project_Loan_Approval.ipynb` öffnen und der Reihenfolge nach ausführen.

## Ergebnisse (aus dem Notebook)

### Test‑Set Metriken

**Logistic Regression**
```
Logistic Regression Metrics:
Accuracy: 0.8776
Precision: 0.8787
Recall: 0.8776
F1-score: 0.8696
```

**Random Forest**
```
Random Forest Metrics:
Accuracy: 0.8776
Precision: 0.8744
Recall: 0.8776
F1-score: 0.8741
```

### Cross‑Validation (Stratified K‑Fold)

**Logistic Regression**
```
Metric      Mean       Std
0   Accuracy  0.746876  0.014576
1  Precision  0.816296  0.013017
2     Recall  0.832257  0.028900
3         F1  0.823785  0.012673
4    ROC AUC  0.701216  0.031429
```

**Random Forest**
```
Metric      Mean       Std
0   Accuracy  0.794319  0.022628
1  Precision  0.802892  0.008644
2     Recall  0.942319  0.027042
3         F1  0.866941  0.015738
4    ROC AUC  0.704772  0.048024
```

**Direkter Vergleich**
```
Model     Logistic Regression  Random Forest
Metric                                      
Accuracy        0.747 ± 0.015  0.794 ± 0.023
Precision       0.816 ± 0.013  0.803 ± 0.009
Recall          0.832 ± 0.029  0.942 ± 0.027
F1              0.824 ± 0.013  0.867 ± 0.016
ROC AUC         0.701 ± 0.031  0.705 ± 0.048
```

➡️ Auf Basis der Cross‑Validation wird im Notebook **Random Forest** als finales Modell empfohlen (insbesondere wegen höherer *Recall*‑Werte).

## Projektstruktur (Vorschlag)

```
.
├── Project_Loan_Approval.ipynb
├── data/
│   ├── loans_modified.csv
│   └── loans_feature.csv
└── README.md
```

## Hinweise

- Das Notebook enthält Stellen, die für **Google Colab** gedacht sind (z.B. `from google.colab import drive`).  
  Für lokale Ausführung kannst du diese Zellen entfernen/überspringen und stattdessen lokale Pfade verwenden.
- Die Visualisierungen (Seaborn/Matplotlib) erscheinen beim Ausführen im Notebook.

## Lizenz

Wenn du eine Lizenz verwenden möchtest, füge z.B. eine `LICENSE` Datei hinzu (MIT/Apache-2.0/GPL etc.).
