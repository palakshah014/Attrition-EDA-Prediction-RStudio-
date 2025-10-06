# Employee Attrition — EDA & Prediction (R)

**Goal:** Explain attrition drivers and predict at-risk employees using logistic regression, with threshold tuning for business trade-offs.

## Highlights
- AUC ≈ **0.80** on holdout.
- Threshold tuning shows:
  - Recall-leaning (thr ≈ 0.22): Acc 0.82, Prec 0.47, Rec 0.68
  - Precision-leaning (thr ≈ 0.37): Acc 0.86, Prec 0.61, Rec 0.46
- Significant drivers (OR, p<.05): **OverTime (≈6.8×)**, **Travel_Frequently (≈5.9×)**, **Single (≈4.8×)**, **Lab Technician (≈4.4×)**.

## Project Structure
employee-attrition-eda-prediction/
├─ README.md
├─ LICENSE
├─ .gitignore
├─ renv.lock                  # (created by renv; optional but recommended)
├─ attrition.Rproj            # (optional, if you use RStudio)
├─ R/
│  ├─ 00_utils.R              # helpers: metrics_at, auc_manual, plotting fns
│  ├─ 01_load_clean.R         # load data, type cleaning, NA handling
│  ├─ 02_eda_plots.R          # ggplot bar charts (dept/role), OR plot
│  ├─ 03_model_logit.R        # logistic model + odds ratios
│  ├─ 04_threshold_tuning.R   # grid scan, F1/precision/recall tradeoffs
│  └─ 05_save_outputs.R       # write metrics, confusion matrix to /outputs
├─ scripts/
│  └─ run_all.R               # sources R/ files in order — one-click reproduce
├─ data/
│  ├─ README.md               # explain where to get data; do NOT commit real PII
│  └─ sample_synthetic.csv    # tiny synthetic example (safe to publish)
├─ figures/
│  ├─ attrition_by_department.png
│  ├─ attrition_by_jobrole.png
│  └─ top_drivers_odds_ratio.png
└─ outputs/
   ├─ metrics_summary.json
   └─ confusion_matrix.csv

## Reproduce
```r
install.packages("renv"); renv::restore()  # or install ggplot2, dplyr manually
source("scripts/run_all.R")


