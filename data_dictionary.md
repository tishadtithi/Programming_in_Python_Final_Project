# Data Dictionary — Ames Housing Dataset

**Source:** Dean De Cock (2011), *Ames, Iowa: Alternative to the Boston
Housing Data as an End of Semester Regression Project*, Journal of
Statistics Education, Vol. 19, No. 3.

**Records:** 2,930 residential property sales in Ames, Iowa (2006–2010).
**Total variables:** 82 (plus target `SalePrice`).

## Target Variable

| Variable    | Type       | Unit  | Description                     |
|-------------|------------|-------|---------------------------------|
| `SalePrice` | Continuous | USD   | Final sale price of the property. This is what our models predict. |

## Identifier Variables (not used as features)

| Variable | Type    | Description                             |
|----------|---------|-----------------------------------------|
| `Order`  | Integer | Row number in the original file.        |
| `PID`    | Integer | Parcel identification number (unique).  |

## Key Feature Groups

Below are the most important feature groups used in this project. The full
official documentation with all 80+ variables is available in the original
De Cock (2011) paper — we do not restate every field, we cite the source.

### Lot / Location

| Variable      | Type        | Unit      | Description                           |
|---------------|-------------|-----------|---------------------------------------|
| `MS Zoning`   | Categorical | —         | General zoning classification.        |
| `Lot Frontage`| Numeric     | linear ft | Street connected to the property.     |
| `Lot Area`    | Numeric     | sq ft     | Lot size in square feet.              |
| `Neighborhood`| Categorical | —         | Physical location within Ames.        |

### Building Type / Style

| Variable      | Type        | Description                              |
|---------------|-------------|------------------------------------------|
| `MS SubClass` | Categorical | Dwelling type involved in the sale.      |
| `Bldg Type`   | Categorical | Type of dwelling.                        |
| `House Style` | Categorical | Style of dwelling.                       |
| `Overall Qual`| Ordinal 1–10| Overall material and finish quality.     |
| `Overall Cond`| Ordinal 1–10| Overall condition rating.                |
| `Year Built`  | Integer     | Original construction year.              |
| `Year Remod/Add` | Integer  | Year of remodel (or Year Built if none). |

### Above-Ground Living Area

| Variable       | Type    | Unit   | Description                             |
|----------------|---------|--------|-----------------------------------------|
| `1st Flr SF`   | Numeric | sq ft  | First-floor square feet.                |
| `2nd Flr SF`   | Numeric | sq ft  | Second-floor square feet.               |
| `Gr Liv Area`  | Numeric | sq ft  | Above-ground living area square feet.   |
| `TotRms AbvGrd`| Integer | rooms  | Total rooms above grade (no bathrooms). |
| `Full Bath`    | Integer | count  | Full bathrooms above grade.             |
| `Half Bath`    | Integer | count  | Half baths above grade.                 |
| `Bedroom AbvGr`| Integer | count  | Bedrooms above grade.                   |

### Basement

| Variable        | Type        | Unit   | Description                              |
|-----------------|-------------|--------|------------------------------------------|
| `Total Bsmt SF` | Numeric     | sq ft  | Total basement area.                     |
| `Bsmt Qual`     | Categorical | —      | Basement height/quality (NA = no basement). |
| `Bsmt Cond`     | Categorical | —      | Basement general condition.              |

### Garage

| Variable      | Type        | Unit   | Description                                |
|---------------|-------------|--------|--------------------------------------------|
| `Garage Type` | Categorical | —      | Garage location (NA = no garage).          |
| `Garage Cars` | Integer     | count  | Size of garage in car capacity.            |
| `Garage Area` | Numeric     | sq ft  | Size of garage in square feet.             |

### Sale

| Variable        | Type        | Description                              |
|-----------------|-------------|------------------------------------------|
| `Mo Sold`       | Integer     | Month sold (1–12).                       |
| `Yr Sold`       | Integer     | Year sold (2006–2010).                   |
| `Sale Type`     | Categorical | Type of sale (e.g., WD = warranty deed). |
| `Sale Condition`| Categorical | Condition of sale (Normal, Abnormal…).   |

## Encoding Conventions

- `NA` values in categorical features such as `Bsmt Qual`, `Garage Type`,
  `Fireplace Qu`, `Pool QC`, `Fence`, `Misc Feature` mean the property does
  not have that feature — this is meaningful and encoded as the category
  `"None"` during preprocessing, not treated as random missing data.
- All other missing values are handled by the preprocessing pipeline
  (median imputation for numeric, most-frequent for categorical), fit on
  the training set only.

## Full Documentation

The complete variable descriptions (all 82 features with categorical
levels) are published in the original De Cock (2011) paper and are cited
in the project report. This file summarizes the fields used in the
project's analysis and modelling.
