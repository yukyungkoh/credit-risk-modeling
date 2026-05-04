# Credit Risk Modeling

End-to-end credit risk modeling pipeline using LendingClub loan data (2007–2020 Q3), covering data preprocessing, exploratory analysis, and default prediction with logistic regression and tree-based models.

## Project Description

This project builds an end-to-end **credit risk modeling pipeline** using LendingClub loan data (2007Q3–2020Q3). The goal is to predict loan default and evaluate how different modeling approaches, ranging from interpretable linear models to more flexible machine learning methods, perform in this setting.

[LendingClub](https://www.lendingclub.com) is a U.S. peer-to-peer (P2P) lending platform where individuals apply for unsecured personal loans issued online. Borrowers span diverse income and credit profiles, often closer to near-prime or subprime segments, and loans are graded based on risk. Investors can select loans to fund using borrower and loan information, earning returns from interest payments. The platform generates revenue through borrower origination fees and investor service fees.

Historically, LendingClub made this data **publicly available** to provide transparency to investors who funded these loans, allowing them to assess risk and make informed investment decisions. The data includes borrower attributes (e.g., income, employment, credit profile), loan characteristics (e.g., amount, term, interest rate), and realized outcomes such as repayment status and default. 

The dataset used in this project is the full LendingClub dataset, the same data used by investors when making real-world investment decisions.

## Project Structure

```
├── data/
│   ├── raw/                  # Raw LendingClub data and data dictionary
│   └── processed/            # Cleaned parquet file
├── notebooks/
│   ├── 1_data_preprocessing.ipynb
│   ├── 2_exploratory_data_analysis.ipynb
│   ├── 3_default_prediction_logistic.ipynb
│   └── 4_default_prediction_tree_models.ipynb
├── src/
│   └── plot_utils.py         # Reusable plotting utilities
└── outputs/
    ├── figures/
    └── tables/
```

## Notebooks

| # | Notebook | Description |
|---|----------|-------------|
| 1 | `1_data_preprocessing.ipynb` | Data cleaning, feature engineering, and export to parquet |
| 2 | `2_exploratory_data_analysis.ipynb` | Univariate distributions and default rate analysis |
| 3 | `3_default_prediction_logistic.ipynb` | Logistic regression model for default prediction |
| 4 | `4_default_prediction_tree_models.ipynb` | Tree-based models (e.g., decision tree, random forest, gradient boosting) |

## Source Modules

### `src/plot_utils.py`

Two plotting functions for EDA:

- **`plot_hist_and_default(df, var_list, ...)`** — For continuous variables: histogram (Panel A) + default rate by quantile bin (Panel B).
- **`plot_dist_and_default(df, var_list, ...)`** — For continuous or categorical variables: share of observations (Panel A) + default rate (Panel B).

Both functions accept a `target` column (default: `'default'`) and optional `var_labels` for display names.

## Data

- **Source**: [LendingClub Loan Data](https://www.kaggle.com/datasets/wordsforthewise/lending-club) (2007–2020 Q3)
- **Raw**: `Loan_status_2007-2020Q3.gzip`, `LCDataDictionary.xlsx`
- **Processed**: `LendingClub_cleaned.parquet`

## Dependencies

```
pandas
matplotlib
seaborn
scikit-learn
pyarrow
jupyter
```
