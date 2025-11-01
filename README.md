
# Advanced Data Mining — Deliverable 1
**Title:** Data Collection, Cleaning, and Exploratory Data Analysis (EDA)  
**Dataset:** Breast Cancer Wisconsin (Diagnostic) via `scikit-learn` 
**Records:** 569 | **Features:** 30 numeric | **Domain:** Healthcare

## Repository Contents
- `Deliverable1_DataCleaning_EDA.ipynb` — complete, commented notebook for loading data, cleaning checks, and EDA (matplotlib-only visualizations).
- `requirements.txt` — minimal dependencies.

## Dataset Summary
This dataset contains 30 numeric features describing cell nuclei characteristics from digitized images of breast mass fine needle aspirates. The target is binary: malignant (0) vs benign (1). The dataset is a standard benchmark derived from the UCI repository and distributed with scikit-learn.

## Data Cleaning Steps
1. **Schema & Types:** Validated feature types; all numeric as expected.
2. **Missingness:** Checked per-column and overall; no missing values detected. (Template code included to impute if needed in other contexts.)
3. **Duplicates:** Checked entire row duplication; none detected.
4. **Noisy Data / Outliers:** Flagged potential extremes with a simple z-score heuristic (|z| > 3). Left raw data intact in this deliverable; provided winsorization template for downstream use if needed.

## EDA Highlights
- **Univariate distributions:** Histograms for key features (e.g., mean radius, perimeter, area, texture, smoothness).
- **Outliers:** Boxplots illustrate spread and potential extremes.
- **Relationships:** Correlation matrix reveals strong blocks among size-related features; top 10 correlated feature pairs are listed.
- **Class comparisons:** Overlaid histograms (malignant vs benign) suggest meaningful separation for several features.

## Key Insights to Guide Modeling
- Highly correlated groups suggest reducing redundancy (feature selection or PCA) or using regularized models.
- Features related to size/shape (e.g., radius, perimeter, area) appear more discriminative — strong candidates for baseline models.
- Consider robust preprocessing for potential outliers (robust scalers, tree-based models) in subsequent deliverables.

## Challenges & Mitigations
- **Missing data handling:** Although none were present, the notebook includes imputation stubs (`SimpleImputer`) for future-proofing pipelines.
- **Multicollinearity:** Detected via correlation analysis; will influence feature engineering and model choice later.
- **Class imbalance risk:** Address with stratified splits, threshold tuning, and metrics beyond accuracy (ROC-AUC, PR curves) in future deliverables.
