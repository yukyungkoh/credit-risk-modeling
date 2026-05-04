# Credit Risk Modeling

End-to-end credit risk modeling pipeline using LendingClub loan data (2007–2020 Q3), covering data preprocessing, exploratory analysis, and default prediction with logistic regression and tree-based models.

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
