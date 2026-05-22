# Titanic-Analysis-ML

## Overview

This project is an independently maintained fork of an original group project completed for COGS108 (Data Science in Practice, Winter 2026) at UC San Diego.

The original repository is preserved under *Titanic-Analysis* on my GitHub profile. Since the original submission, this fork has been extended and refined by Adrianne as an ongoing exploratory and reproducible data science project.

The project investigates which passenger characteristics influenced survival aboard the Titanic using statistical analysis, exploratory data analysis (EDA), and machine learning models.

> **Note:** This repository represents an active and non-final iteration of the analysis notebook. Methods, visualizations, feature engineering approaches, and evaluation procedures may continue to evolve as the project is refined.

---

# Motivation

The original course project focused on introducing applied data science workflows including:

- data cleaning
- exploratory analysis
- hypothesis testing
- introductory predictive modeling

This fork expands that foundation by:

- improving reproducibility
- refining preprocessing methodology
- strengthening statistical interpretation
- improving model transparency and evaluation]

An additional goal of this fork is to reduce the “black-box” nature of predictive modeling by emphasizing interpretability alongside predictive performance.

---

# Dataset

This project uses the Titanic passenger dataset, containing demographic, socioeconomic, and travel-related information for passengers aboard the RMS Titanic.

Key variables include:

- Passenger class (`pclass`)
- Age
- Sex
- Fare
- Family relationships aboard (`sibsp`, `parch`)
- Embarkation location
- Survival outcome (`survived`)

Primary dataset source:

- https://www.kaggle.com/datasets/shraddha4ever20/titanic-datset

The dataset used in this analysis contains 891 passenger records and serves as a representative sample rather than the complete Titanic manifest.

---

# Methods

## Data Cleaning & Preprocessing

The preprocessing pipeline includes:

- Missing value analysis and imputation
- Statistical testing of missingness patterns
- Removal of highly incomplete features
- Encoding categorical variables
- Feature engineering
- Standardization/scaling for modeling

Specific preprocessing steps include:

- Median age imputation grouped by demographic categories
- Removal of the `deck` column due to substantial missingness
- Encoding embarkation variables
- Creation of engineered features such as:
  - `family_size`
  - `is_child`
  - `is_male`

The project also evaluates potential feature redundancy and proxy relationships between:

- passenger class
- fare
- embarkation location

---

# Exploratory Data Analysis (EDA)

The analysis investigates several central research questions.

## Women and Children First

The notebook evaluates whether the historical “Women and Children First” evacuation policy had a measurable impact on survival outcomes.

This includes:

- gender-based survival comparisons
- age-group analysis
- chi-squared testing
- distribution visualizations

## Socioeconomic Status & Passenger Class

Passenger class is analyzed as a proxy for socioeconomic status.

The project explores:

- class-based survival disparities
- fare distributions
- embarkation differences
- class composition across ports

## Feature Relationships

Additional analysis examines:

- correlation structures
- potential multicollinearity
- distribution skew
- interaction effects between variables

---

# Modeling

Several predictive models are implemented and evaluated, including:

- Logistic Regression (baseline)
- Logistic Regression with transformed features
- GridSearchCV-tuned Logistic Regression
- Support Vector Machine (SVM)

Evaluation metrics include:

- Accuracy
- ROC-AUC
- Precision
- Recall
- F1-score
- Confusion matrices

The workflow emphasizes both predictive performance and interpretability rather than optimization alone.

---

# Current Results

The latest iteration of the notebook suggests:

- Sex was the strongest predictor of survival
- Passenger class strongly influenced survival probability
- Children showed moderately improved survival outcomes
- Fare and embarkation location contained partially overlapping socioeconomic information
- Logistic Regression achieved stable baseline performance (~80% test accuracy)
- SVM models slightly improved predictive performance while reducing interpretability

These findings support historical evidence that survival outcomes aboard the Titanic were influenced by structured social and demographic factors rather than pure randomness.

> Because this repository is still under active refinement, model metrics and conclusions may change as preprocessing methods, feature engineering, and evaluation procedures improve.

---

# Reproducibility

This repository is structured to support reproducible analysis using publicly available data and standard Python data science libraries.

## Reproducing the Analysis

Clone the repository:

```bash
git clone <repo-url>
cd <repo-folder>
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Launch Jupyter:

```bash
jupyter notebook
```

Run notebooks in order:

1. Data Cleaning
2. Exploratory Data Analysis
3. Modeling & Evaluation

---

## Recomputing Results

All statistics, figures, and model outputs are generated programmatically from the dataset at runtime.

To recompute results:

- replace the dataset in the `/data` directory
- or pull updated dataset versions and rerun the notebooks

As long as the dataset schema remains compatible, all:

- visualizations
- summary statistics
- model metrics
- evaluations

will automatically regenerate from the current dataset.

---

## Determinism

For reproducibility:

- `random_state=42` is used where applicable
- train/test splits are fixed
- preprocessing steps are explicitly documented

The pipeline is designed so that analytical outputs are derived programmatically rather than manually hardcoded.

---

# Tools & Libraries

- Python
- pandas
- numpy
- scikit-learn
- scipy
- statsmodels
- matplotlib
- seaborn
- Jupyter Notebook

---

# Ethics & Limitations

This project includes discussion of:

- sampling limitations
- proxy-variable bias
- historical/social context
- survivorship bias
- model interpretability concerns

Several limitations remain important:

- the dataset excludes crew members
- some features required imputation
- many real-world survival factors were unobserved

The project therefore avoids treating predictive accuracy as equivalent to causal certainty.

---

# Attribution

Original group project completed for COGS108 at UC San Diego (Winter 2026).

This repository is a fork and independent continuation maintained by Adrianne.

Contributors to the original project include:

- Adrianne Steven See
- Kyle Wu
- Connor Wu
- Harvey Sandhu
- Teddy Nguyen

---

# Future Improvements

Planned future refinements may include:

- cleaner project modularization
- notebook-to-script pipeline conversion
- improved feature selection workflows
- additional model comparisons

Possible repository restructuring:

```text
/data
/notebooks
/src
/models
/figures
/reports
```

---

# How to Run

```bash
git clone <repo-url>
cd <repo-folder>
pip install -r requirements.txt
jupyter notebook
```

---

# Key Takeaways

- Data preprocessing choices significantly impacted model performance
- Simple interpretable models performed competitively with more complex approaches
- Feature engineering improved both model stability and interpretability
- Statistical context and ethical framing were important alongside predictive accuracy
- Reproducibility and documentation are critical components of applied data science workflows
