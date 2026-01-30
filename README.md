# 📈 Predictive Modelling of Social Media Trend Emergence  
🎓 **Final Year Project (CM3070)**

---

## 🌟 Overview
This project explores whether **early-stage metadata and lightweight content signals** can be used to predict the **emergence of trending short-form video content**.

The study focuses on a comparison between **YouTube Shorts** and **TikTok Shorts**, analysing how different platform formats and early engagement signals influence trend formation.

📚 This work was completed as a **Final Year Project** for the  
**BSc (Hons) Computer Science — University of London**,  
studied via **SIM (distance learning)**, with academic direction provided by **Goldsmiths, University of London**.

---

## ❓ Problem Statement
Short-form video trends emerge extremely quickly — often within hours or days.

This project investigates:

> **Can early observable metadata be used to predict whether a short-form video will become trending?**

Instead of relying on long-term engagement history, the focus is on **early-stage signals**, reflecting realistic constraints faced in real-world prediction scenarios.

---

## 📊 Data Sources
- 📺 **YouTube Shorts** — collected using the *YouTube Data API*
- 🎵 **TikTok Shorts** — sourced from publicly available datasets (Kaggle)

🗺️ Data is scoped to the **United States region** and covers content from the **past 2–3 years** to ensure relevance and consistency.

---

## 🛠️ Methodology

### 🔄 1. Data Pipeline
An end-to-end academic data pipeline was designed and implemented, covering:
- Data collection & ingestion  
- Validation and cleaning  
- Feature extraction & preprocessing  
- Train/test splitting  
- Model training and evaluation  

The pipeline was structured to simulate **real-world data workflows**, including handling missing values, noisy data, and class imbalance.

---

### 🧩 2. Feature Engineering
Features were derived from:
- Early engagement metrics (views, likes, comments)
- Video metadata (duration, posting time, category)
- Textual features from titles/descriptions using **TF-IDF**

⚖️ Class imbalance was addressed using **SMOTE**, and feature importance analysis was performed to identify key predictive signals.

---

### 🤖 3. Models Implemented
The following models were trained and compared:
- Logistic Regression  
- Random Forest  
- XGBoost  

📏 Evaluation metrics:
- F1-score  
- Precision & Recall  
- Confusion Matrix  

This enabled comparison between interpretable baselines and more complex ensemble models.

---

## 📈 Results & Evaluation
- Models achieved **moderate predictive performance** using early-stage features alone.
- Tree-based models (**Random Forest, XGBoost**) generally outperformed linear baselines.
- Differences were observed between **YouTube Shorts and TikTok Shorts**, suggesting platform-specific trend dynamics.
- Results highlight both the **potential and limitations** of early trend prediction.

A detailed evaluation and discussion of limitations is included in the final report.

---

## 💻 Tools & Technologies
- 🐍 **Python**
- 🧮 **SQL**
- 📓 **Jupyter Notebook**
- **pandas**, **NumPy**
- **scikit-learn**
- **XGBoost**
- **SMOTE (imbalanced-learn)**
- **YouTube Data API**

---

## 📁 Repository Structure
```text
├── notebook.ipynb        # Main implementation and analysis
├── report.pdf            # Final academic report
├── figures/              # Visualisations and plots
└── data/                 # Processed datasets (where permitted)

```
⚠️ Limitations

Like most academic and data-driven projects, this study has several constraints that should be considered when interpreting the results:

⏳ API rate limits restricted the total volume and frequency of data collection, particularly for YouTube Shorts.

🎵 TikTok data was obtained from publicly available datasets rather than a live API, limiting control over data granularity and freshness.

🏷️ Trend labels are platform-dependent and rely on each platform’s definition of what constitutes “trending.”

🧪 Results are exploratory and academic in nature, intended to study patterns rather than deliver production-ready predictions.

All limitations are discussed transparently and in greater detail in the final report.

🎯 Learning Outcomes

Through this project, I gained experience in:

Designing structured data pipelines

Working with noisy, real-world datasets

Feature engineering and model comparison

Handling class imbalance in machine learning tasks

Documenting system design, assumptions, and limitations

📌 Disclaimer

This project was completed for academic purposes only.
It does not represent a production-ready or commercial forecasting system.

