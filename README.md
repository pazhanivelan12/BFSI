# 🏦 Banking Dashboard – Exploratory Data Analysis

## Project Overview

This project performs **Exploratory Data Analysis (EDA)** on a banking client dataset (`Banking.csv`) using Python. The insights derived from this analysis were used to build an interactive **Banking Dashboard** (built in Power BI), visualizing key metrics such as total loans, deposits, checking/savings accounts, and business lending — filterable by **Joining Year** and **Gender**.

---

## Dashboard Preview

The dashboard includes the following KPI cards:

| Metric               | Value     |
|----------------------|-----------|
| Total Clients        | 67        |
| Total Loan           | 101.46M   |
| Total Deposit        | 88.20M    |
| Checking Accounts    | 19.32M    |
| Savings Accounts     | 18.53M    |
| Business Lending     | 54.08M    |

**Filters available:** Joining Year (2008, 2014, 2019, 2020, 2021) | Gender (Male / Female)

---

## Dataset

- **File:** `Banking.csv`
- **Rows:** 500 (approx.)
- **Columns:** 25

### Key Columns

| Column | Description |
|---|---|
| `Client ID` | Unique identifier for each client |
| `Name` | Client name |
| `Age` | Client age |
| `Joined Bank` | Date the client joined the bank |
| `Nationality` | Client nationality (American, African, European, etc.) |
| `Occupation` | Job title |
| `Fee Structure` | High / Mid / Low |
| `Loyalty Classification` | Jade / Gold / Silver / Platinum |
| `Estimated Income` | Annual income estimate |
| `Bank Deposits` | Total deposits |
| `Checking Accounts` | Checking account balance |
| `Saving Accounts` | Savings account balance |
| `Business Lending` | Business loan amount |
| `Bank Loans` | Personal loan amount |
| `Credit Card Balance` | Outstanding credit card balance |
| `Risk Weighting` | Risk score (1–5) |
| `GenderId` | Encoded gender |
| `Properties Owned` | Number of properties owned |

---

## Project Structure

```
banking-eda/
│
├── Banking.csv               # Source dataset
├── working.ipynb             # Main EDA notebook
└── README.md                 # Project documentation
```

---

## Notebook Summary (`working.ipynb`)

The notebook contains **15 cells** covering the following analysis steps:

### 1. Imports
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np
```

### 2. Data Loading & Preview
- Loads `Banking.csv` into a DataFrame
- Previews the first 5 rows

### 3. Data Inspection
- `df.shape` – dimensions of the dataset
- `df.info()` – column types and null counts
- `df.describe()` – statistical summary of numerical columns

### 4. Feature Engineering
- Creates an **Income Band** column by binning `Estimated Income`:
  - `Low` → < 100,000
  - `Med` → 100,000 – 300,000
  - `High` → > 300,000

### 5. Univariate Analysis
- Bar chart of Income Band distribution
- Value counts for categorical columns: `BRId`, `GenderId`, `IAId`, `Amount of Credit Cards`, `Nationality`, `Occupation`, `Fee Structure`, `Loyalty Classification`
- Histogram plots for each categorical column (except Occupation)

### 6. Bivariate Analysis
- Cross-tab plots of categorical features against target variables
- Relationship exploration between demographics and financial metrics

### 7. Correlation Heatmap
- Correlation matrix for numerical columns:
  - `Estimated Income`, `Superannuation Savings`, `Credit Card Balance`, `Bank Loans`, `Bank Deposits`, `Checking Accounts`, `Saving Accounts`, and others

---

## Technologies Used

| Tool | Purpose |
|---|---|
| Python 3 | Core programming language |
| Pandas | Data loading, cleaning, manipulation |
| Matplotlib | Plotting and visualization |
| Seaborn | Statistical visualizations |
| NumPy | Numerical operations |
| Google Colab | Notebook execution environment |
| Power BI | Interactive dashboard (separate file) |

---

## Key Insights

- **Income segmentation** reveals a skewed distribution, with most clients in the Low–Mid income bands.
- **Nationality and Occupation** are diverse, indicating a broad client base.
- **Loyalty classification** (Jade, Gold, Silver, Platinum) correlates with fee structure and estimated income.
- **Business Lending (54.08M)** is the largest loan category, indicating a strong commercial banking segment.
- **Gender and Joining Year** filters on the dashboard allow for trend analysis across cohorts.

---

## How to Run

1. Clone or download this repository.
2. Place `Banking.csv` in the root directory (or update the file path in the notebook).
3. Open `working.ipynb` in **Jupyter Notebook**, **JupyterLab**, or **Google Colab**.
4. Run all cells in order.

---

## Author

**Pazhani**  
Business Analytics | BFSI Domain | SQL · Power BI · Python · Excel

---

## License

This project is for educational and portfolio purposes only. The dataset used is synthetic/sample data.
