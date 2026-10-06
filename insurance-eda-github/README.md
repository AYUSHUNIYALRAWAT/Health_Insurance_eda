# Insurance Data Analysis & Exploratory Data Analysis (EDA)

A Python-based **Exploratory Data Analysis (EDA)** project on health insurance data.  
The project uses **Pandas, NumPy, Matplotlib, and Seaborn** to inspect the dataset, identify data-quality issues, visualize distributions, analyze correlations, clean categorical variables, encode features, and create a BMI-based feature.

## 📌 Project Overview

This project focuses on understanding the factors present in an insurance dataset and preparing the data for possible downstream analytics or machine-learning work.

The notebook covers:

- Dataset loading and inspection
- Shape, data types, descriptive statistics, and column inspection
- Missing-value checking
- Duplicate-record detection and removal
- Distribution analysis of numerical variables
- Count plots for categorical variables
- Outlier inspection using box plots
- Correlation analysis using a heatmap
- Categorical data cleaning and encoding
- One-hot encoding of the `region` column
- BMI-category feature engineering
- Final numerical dataset preparation

> **Note:** This repository contains EDA and preprocessing only. It does not train or evaluate a machine-learning model.

---

## 📊 Dataset

The dataset contains **1,338 rows and 7 original columns**.

| Column | Description |
|---|---|
| `age` | Age of the insurance beneficiary |
| `sex` | Sex of the beneficiary |
| `bmi` | Body Mass Index |
| `children` | Number of children/dependents |
| `smoker` | Smoking status |
| `region` | Residential region |
| `charges` | Insurance charges |

### Data quality checks

- Missing values: **0 in all original columns**
- Duplicate rows found: **1**
- Rows after duplicate removal: **1,337**

### Numerical summary

| Variable | Mean | Min | Max |
|---|---:|---:|---:|
| `age` | 39.21 | 18 | 64 |
| `bmi` | 30.66 | 15.96 | 53.13 |
| `children` | 1.09 | 0 | 5 |
| `charges` | 13,270.42 | 1,121.87 | 63,770.43 |

---

## 🔍 EDA Performed

### 1. Dataset inspection

The notebook uses:

```python
data.shape
data.info()
data.describe()
data.isnull().sum()
data.columns
```

to understand the dataset structure and quality.

### 2. Distribution analysis

Histograms with KDE are created for:

- Age
- BMI
- Number of children
- Insurance charges

### 3. Categorical analysis

Count plots are created for:

- Number of children
- Sex
- Smoking status

### 4. Outlier analysis

Box plots are used for numerical variables to visually inspect their distributions and potential outliers.

### 5. Correlation analysis

A correlation heatmap is used to examine relationships among numerical variables.

---

## 🧹 Data Cleaning & Preprocessing

The notebook performs the following preprocessing steps:

1. Creates a copy of the original dataset.
2. Removes duplicate records.
3. Standardizes text values using `strip()` and `lower()`.
4. Encodes:
   - `sex` → `is_female`
   - `smoker` → `is_smoker`
5. One-hot encodes `region` using `drop_first=True`.
6. Creates a new `bmi_category` feature using these ranges:
   - Underweight: BMI ≤ 18.4
   - Normal: 18.5–24.9
   - Overweight: 25.0–29.9
   - Obese: BMI ≥ 30
7. One-hot encodes the BMI categories.
8. Converts the final dataframe to integer values.

### Final engineered features

The final dataframe contains:

```text
age
is_female
bmi
children
is_smoker
charges
region_northwest
region_southeast
region_southwest
bmi_category_normal
bmi_category_overweight
bmi_category_obese
```

`northeast` and the first BMI category are represented implicitly because `drop_first=True` is used during one-hot encoding.

---

## 🛠️ Technologies Used

- **Python**
- **Pandas** — data manipulation and preprocessing
- **NumPy** — numerical operations
- **Matplotlib** — visualization
- **Seaborn** — statistical visualization
- **Jupyter Notebook** — interactive analysis

---

## 📁 Project Structure

```text
insurance-eda/
│
├── EDA_PROJECT.ipynb       # Main EDA notebook
├── insurance.csv           # Dataset
├── README.md                # Project documentation
├── DATA_DICTIONARY.md       # Dataset column reference
├── PROJECT_SUMMARY.md       # Short project summary
├── requirements.txt         # Python dependencies
├── .gitignore               # Git ignored files
└── LICENSE                  # MIT License
```

---

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/insurance-eda.git
cd insurance-eda
```

### 2. Create a virtual environment (recommended)

```bash
python -m venv venv
```

Activate it:

**macOS/Linux**
```bash
source venv/bin/activate
```

**Windows**
```bash
venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Start Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
EDA_PROJECT.ipynb
```

Run the notebook cells from top to bottom.

---

## 📈 Key Observations From the Dataset

- The dataset contains **1,338 records** before duplicate removal.
- There are **no missing values** in the original dataset.
- **1 duplicate row** was identified and removed during preprocessing.
- The dataset contains **274 smokers** and **1,064 non-smokers**.
- The largest regional group is `southeast` with **364 records**.
- BMI was transformed into four analytical categories for feature engineering.
- The project prepares categorical variables for numerical analysis through encoding.

These observations describe the dataset; they should not be interpreted as causal conclusions.

---

## 🎯 Learning Outcomes

This project demonstrates practical skills in:

- Exploratory Data Analysis
- Data cleaning
- Missing-value inspection
- Duplicate handling
- Data visualization
- Correlation analysis
- Categorical encoding
- Feature engineering
- Pandas data manipulation
- Preparing a dataset for further analytics

---

## 🔮 Possible Future Improvements

The current project can be extended with:

- Deeper statistical analysis
- Group-wise analysis of insurance charges
- Interactive dashboards using Power BI or Tableau
- Regression modeling to predict insurance charges
- Model evaluation and comparison
- More robust outlier treatment
- Automated EDA reporting

---

## 👤 Author

**Ayush Rawat**

B.Tech Data Science Student

---

## 📄 License

This project is available under the MIT License. See [`LICENSE`](LICENSE) for details.
