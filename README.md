# Python Final Term Project — House Price Estimation (Regression)

**Course:** Programming in Python — Summer 25-26 Semester
**Pathway:** Regression
**Dataset:** Ames Housing (De Cock, 2011)

---

## 1. Project Overview

This project predicts residential house sale prices in Ames, Iowa using the
Ames Housing dataset (2,930 records, 82 features). It follows the full
data-science workflow required by the course:

1. Problem formulation
2. Data provenance
3. Data audit
4. Exploratory analysis
5. Split design (leakage-safe)
6. Preprocessing (fit on training data only)
7. Baseline (mean predictor)
8. Model development (Linear Regression, Random Forest)
9. Final evaluation on untouched test set
10. Interpretation, limitations, and error analysis

## 2. File Structure

```
python-final-term-project/
├── data/
│   ├── raw/AmesHousing.csv          # untouched original
│   └── processed/                   # generated at run-time
├── notebooks/
│   └── house_price_analysis.ipynb   # main runnable notebook
├── report/
│   └── project_report.pdf           # final written report
├── figures/                         # generated plots
├── README.md
├── requirements.txt
└── data_dictionary.md
```

## 3. Environment Setup

Python version: 3.14.5

```bash
# 1. Create a virtual environment
python -m venv venv

# 2. Activate it
# Windows:
venv\Scripts\activate
# macOS / Linux:
source venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt
```

## 4. Data Access

The dataset `AmesHousing.csv` is included in `data/raw/`.

- **Source:** Dean De Cock (2011), *Ames, Iowa: Alternative to the Boston
  Housing Data as an End of Semester Regression Project*,
  Journal of Statistics Education, Vol. 19, No. 3.
- **License:** Publicly available for academic use.
- **Data dictionary:** see `data_dictionary.md`.

## 5. Run Order

Open the notebook and run all cells top-to-bottom from a clean kernel:

```bash
jupyter notebook notebooks/house_price_analysis.ipynb
```

The notebook executes:
1. Data loading and validation
2. Data audit (missing values, duplicates, ranges)
3. Exploratory analysis and visualization
4. Train/test split (random_state = 42, stratified by price bin)
5. Preprocessing pipeline (imputation, encoding, scaling)
6. Baseline (mean predictor)
7. Model training: Linear Regression and Random Forest
8. Final evaluation on the untouched test set
9. Comparison table and diagnostic plots
10. Error analysis and interpretation

## 6. Expected Outputs

- Metrics table comparing Baseline, Linear Regression, and Random Forest
  (MAE, RMSE, R²).
- Diagnostic plots (target distribution, feature relationship, residual plot,
  model comparison) saved under `figures/`.
- Final selected model clearly labelled.

## 7. Reproducibility

- `random_state = 42` is used consistently for splitting and Random Forest.
- Package versions are pinned in `requirements.txt`.
- The notebook runs top-to-bottom without any manual steps.


## 8. Academic Integrity

All code, analysis, and interpretation are the group's own work.
External sources (documentation, dataset origin) are cited in the report.
