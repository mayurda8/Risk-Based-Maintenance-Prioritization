# Risk-Based-Maintenance-Prioritization
Decision-oriented predictive maintenance using engine degradation data, explainable ML, and risk-based prioritization.


## 📌 Overview
This project presents a **decision-oriented predictive maintenance framework** that transforms raw engine sensor data into actionable maintenance priorities.

Rather than focusing solely on predicting Remaining Useful Life (RUL), the problem is reframed as a **near-term failure risk classification task**, aligning the analysis with real-world maintenance decision-making.

The final outcome is not just a prediction model, but a **ranked list of assets** that require immediate attention.

---

## 📊 Dataset
**NASA CMAPSS Turbofan Engine Degradation Dataset**

- 100 independent engine lifecycles  
- 21 sensor measurements recorded per operational cycle  
- Significant variability in engine lifetimes (early and late failures)  

This variability highlights the limitations of fixed maintenance thresholds and motivates a risk-based approach.

---

## 🎯 Problem Framing
Traditional maintenance strategies rely on:
- Fixed cycle thresholds, or
- Exact Remaining Useful Life (RUL) estimates  

In practice, maintenance teams need answers to a different question:

> *Which engines should we act on first?*

To address this, a **25-cycle failure risk horizon** was defined, converting the task into a **near-term failure risk classification problem** suitable for proactive intervention.

---

## 🧠 Feature Engineering
Raw sensor readings were intentionally not used directly.  
Instead, degradation behavior was captured using engineered indicators:

- **Rolling stress indicators** – to represent sustained operational load  
- **Volatility measures** – to capture instability prior to failure  
- **Rate-of-change features** – to model wear dynamics  

Visual analysis confirmed that engineered features revealed degradation patterns that were not apparent in raw sensor signals.

---

## 🤖 Modeling Approach
- **Model:** Random Forest Classifier  
- **Validation Strategy:** Engine-level train/test split to prevent lifecycle leakage  
- **Evaluation Focus:** Recall for near-term failure cases  

**Result:**  
The model achieved approximately **79% recall** for engines approaching failure, prioritizing the detection of high-risk assets where missed failures would be operationally costly.

---

## 🔍 Model Interpretability
Feature importance analysis showed that:

- Sustained stress patterns were the strongest contributors to failure risk  
- Volatility and rate-based features provided complementary signals  

These findings align with domain intuition and increase trust in the model’s predictions.

---

## 🚀 Decision-Oriented Output
The key contribution of this project is a **risk-priority score** that converts model outputs into actionable decisions.

The score integrates:
- Predicted failure probability  
- Relative stress intensity  
- Urgency based on remaining life  

The final output is a **ranked list of engines** requiring immediate maintenance attention, enabling focused and proactive resource allocation.

---

## ✅ Key Takeaway
Predictive models create value only when translated into decisions.

This project demonstrates how machine learning, when combined with thoughtful feature engineering and risk framing, can support **proactive and prioritized maintenance strategies** rather than reactive monitoring.


## 🛠️ Tools & Technologies
- Python  
- Pandas, NumPy  
- Scikit-learn  
- Matplotlib  
- Jupyter / Google Colab  

---

## 📌 Notes
- The dataset is publicly available from NASA’s Prognostics Data Repository.
- The project focuses on **decision support**, not just prediction accuracy.
