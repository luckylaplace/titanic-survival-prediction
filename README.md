# 🚢 Titanic Survival Prediction

A complete data science project analyzing the Titanic dataset to predict passenger survival using exploratory data analysis (EDA), feature engineering, and machine learning.

> **Kaggle Competition:** [Titanic — Machine Learning from Disaster](https://www.kaggle.com/competitions/titanic)

---

## 📁 Project Structure

```
titanic-project/
├── data/
│   ├── raw/                  # Original Kaggle datasets (train.csv, test.csv, gender_submission.csv)
│   └── processed/            # Cleaned datasets after feature engineering
├── notebooks/
│   ├── 01_eda.ipynb                 # Exploratory Data Analysis
│   ├── 02_feature_engineering.ipynb # Feature creation & data cleaning
│   ├── 03_modeling.ipynb            # Model training & evaluation
│   └── 04_predictions.ipynb         # Test set predictions & submission
├── docs/
│   ├── hypotheses.md         # Pre-analysis hypotheses & validation results
│   └── eda_findings.md       # Summary of EDA findings
├── figures/                  # All generated visualizations
├── submissions/              # Kaggle submission files
├── .gitignore
└── README.md
```

---

## 🔍 Key Findings

| Factor | Survival Impact |
|--------|----------------|
| **Gender** | Women: **~74%** vs Men: **~19%** — strongest predictor |
| **Class** | 1st: **63%**, 2nd: **47%**, 3rd: **24%** |
| **Age** | Children (0-12): **~58%**, Elderly (60+): **~23%** |
| **Family Size** | 2-4 members: up to **~72%**, Solo: **~30%** |
| **Fare** | Higher fare → significantly higher survival |
| **Title** | Mrs: **~79%**, Miss: **~70%**, Mr: **~16%** |

### Survival Highlights
- **1st class women** had a **96.8%** survival rate.
- **3rd class men** had the lowest at **13.5%**.
- The "women and children first" rule was clearly reflected in the data.

---

## 📊 Sample Visualizations

<p align="center">
  <img src="figures/survival_by_gender.png" width="45%" alt="Survival by Gender" />
  <img src="figures/survival_by_class.png" width="45%" alt="Survival by Class" />
</p>
<p align="center">
  <img src="figures/age_analysis.png" width="45%" alt="Age Analysis" />
  <img src="figures/correlation_matrix.png" width="45%" alt="Correlation Matrix" />
</p>
<p align="center">
  <img src="figures/feature_importance.png" width="45%" alt="Feature Importance" />
  <img src="figures/family_size_survival.png" width="45%" alt="Family Size Survival" />
</p>

---

## ⚙️ Methodology

### 1. Exploratory Data Analysis (`01_eda.ipynb`)
- Dataset inspection, missing data analysis, univariate & bivariate analysis.
- 21 visualizations generated covering survival rates across all key features.
- Hypotheses tested and documented in [`docs/hypotheses.md`](docs/hypotheses.md).

### 2. Feature Engineering (`02_feature_engineering.ipynb`)
- **FamilySize** = SibSp + Parch + 1
- **IsAlone** = 1 if FamilySize == 1
- **Title** extracted from Name (Mr, Mrs, Miss, Master, Rare)
- **Age** imputed using Pclass × Sex median
- **Embarked** imputed with mode; **Fare** imputed with median

### 3. Modeling (`03_modeling.ipynb`)
- **Random Forest Classifier** — primary model
- **Logistic Regression** — baseline comparison
- 5-fold cross-validation for robust evaluation
- Feature importance analysis

### 4. Predictions (`04_predictions.ipynb`)
- Final model applied to test set
- Submission file generated for Kaggle

---

## 🛠️ Tech Stack

- **Python 3.11**
- **pandas** & **NumPy** — data manipulation
- **Matplotlib** & **Seaborn** — visualization
- **scikit-learn** — machine learning

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/luckylaplace/titanic-survival-prediction.git
cd titanic-project
```

### 2. Download the data
Download the dataset from [Kaggle](https://www.kaggle.com/competitions/titanic/data) and place the CSV files in `data/raw/`:
```
data/raw/
├── train.csv
├── test.csv
└── gender_submission.csv
```

### 3. Install dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### 4. Run the notebooks
```bash
jupyter notebook
```
Open notebooks in order: `01_eda.ipynb` → `02_feature_engineering.ipynb` → `03_modeling.ipynb` → `04_predictions.ipynb`

---

## 📄 Documentation

- [**Hypotheses & Findings**](docs/hypotheses.md) — Pre-analysis predictions validated against data
- [**EDA Findings**](docs/eda_findings.md) — Comprehensive analysis summary with visualizations

---

## 📝 License

This project is for educational purposes. The Titanic dataset is provided by [Kaggle](https://www.kaggle.com/competitions/titanic).
