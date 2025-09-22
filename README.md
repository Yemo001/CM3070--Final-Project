# CM3070--Final-Project

# This is the codes and reports for various submitted works throughout my FYP Data Science Project.

Overview

This repository contains all code, figures and reports for my BSc CS Final Year Project (UoL/Goldsmiths).
The project builds a lightweight, interpretable pipeline to predict trend emergence on YouTube Shorts using only early-available metadata (publish time, title, views/likes/comments) rather than full content analysis.

Key points:

Models compared: Logistic Regression (baseline), Random Forest, XGBoost

Features: views_per_day, like_ratio, title_length, publish hour/weekday, category, and TF-IDF over title+description

Imbalance handling: SMOTE applied on the training split only

Evaluation: Accuracy, Precision, Recall, F1, ROC-AUC, Confusion Matrix, ROC/PR curves

Limitation: YouTube Data API quotas (daily cap) — scripts pause when quota is exhausted (see “Quotas & Ethics”)
Run the notebook

Run all cells in order. The pipeline will:

Collect recent Shorts metadata (with region/category fallbacks)

Clean & merge into data/clean/yt_clean.csv
What the models do

Logistic Regression (balanced class weights) provides a transparent baseline over sparse TF-IDF + tabular features.

Random Forest captures non-linear interactions; we report feature importances for interpretability.

XGBoost tests a stronger ensemble; we prioritise clarity over heavy hyper-tuning.

Target label: binary viral defined by the top-quartile of views_per_day (or 48-hour threshold for Shorts), stratified train/test split.

Reproducibility & results

Cross-validation: 5-fold on the training set (report the mean ± std of Accuracy/Precision/Recall/F1/ROC-AUC).

Held-out test: Confusion matrix, ROC and PR curves saved to /artifacts.

Key figures to cite in Chapter 5:

fig_cv_f1_boxplot.png – model stability across folds

fig_roc_lr_rf.png – ROC comparison on test set

fig_pr_curves.png – PR curves (useful under imbalance)

fig_cm_rf.png – test confusion matrix (Random Forest)

fig_rf_importances.png – top features driving predictions

You can also refer to:

metrics_test.csv – table of final test metrics by model

test_summary.csv – short formatted summary for the report

Engineer features (ratios, TF-IDF, time features)

Train Logistic Regression, Random Forest, XGBoost

Evaluate and save figures/CSVs under artifacts/

Data collection, ethics & quotas

Data is collected via official YouTube Data API v3 using authenticated requests.

Only public metadata is used (no personal data, no scraping of private content).

Quota limits: The API has a daily request quota. When the limit is hit, collection stops and can be resumed after the 24-hour reset window. This affected iteration speed during development and is noted as a limitation in the report.

Some categories are not available in all regions. The notebook includes a fallback that fetches all-category pages and filters locally.

Limitations & future work

API rate limits slow down large, multi-region collection; batching and caching would help.

Label definition (top-quartile / 48-hour threshold) is a pragmatic proxy; platform-level “trending” signals are not public.

Text features: Lightweight TF-IDF keeps things explainable; future work could try BERT embeddings or thumbnail/vision features if resources allow.
