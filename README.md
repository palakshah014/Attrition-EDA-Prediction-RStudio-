# Employee Attrition — EDA & Prediction (R)

**Goal:** Explain attrition drivers and predict at-risk employees using logistic regression, with threshold tuning for business trade-offs.

## Highlights
- AUC ≈ **0.80** on holdout.
- Threshold tuning shows:
  - Recall-leaning (thr ≈ 0.22): Acc 0.82, Prec 0.47, Rec 0.68
  - Precision-leaning (thr ≈ 0.37): Acc 0.86, Prec 0.61, Rec 0.46
- Significant drivers (OR, p<.05): **OverTime (≈6.8×)**, **Travel_Frequently (≈5.9×)**, **Single (≈4.8×)**, **Lab Technician (≈4.4×)**.

## Project Structure
(see tree above)

## Reproduce
```r
install.packages("renv"); renv::restore()  # or install ggplot2, dplyr manually
source("scripts/run_all.R")


