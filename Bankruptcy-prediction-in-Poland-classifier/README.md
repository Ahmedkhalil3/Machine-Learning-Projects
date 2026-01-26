# Bankruptcy Prediction in Poland 🇵🇱  
**Imbalanced Classification with Threshold-Tuned Random Forest**

## 📌 Project Overview
This project focuses on predicting **corporate bankruptcy** using financial ratios from Polish companies.  
The dataset is **highly imbalanced**, making accuracy an unsuitable metric. Instead, the project emphasizes **recall-driven risk screening**, supported by proper resampling, cross-validation, and threshold tuning.

The final model is a **Random Forest classifier**, carefully tuned and evaluated using **ROC-AUC** and **precision–recall trade-offs**, making it suitable for **early-warning bankruptcy screening systems**.

---

## 🎯 Problem Statement
Bankruptcy is a **rare but costly event**.  
Failing to detect a bankrupt company (false negative) is significantly more expensive than incorrectly flagging a healthy one (false positive).

**Objective:**  
Build a model that detects as many bankrupt companies as possible while keeping false alarms at a manageable level.

---

## 📊 Dataset Description
- **Source:** Polish bankruptcy dataset (financial ratios)
- **Observations:** 9,977 companies
- **Features:** 64 numerical financial indicators
- **Target:** `bankrupt` (True / False)
- **Class distribution:**
  - Non-bankrupt: ~95.3%
  - Bankrupt: ~4.7%

---

## 🧠 Methodology

### 1. Data Preparation
- Loaded compressed JSON data (`.json.gz`)
- Set `company_id` as index
- All features are numerical
- Missing values handled using **median imputation**

### 2. Exploratory Data Analysis (EDA)
- Verified severe class imbalance
- Examined feature distributions and outliers
- Used **quantile clipping** for visualization only

### 3. Train–Test Split
- 80/20 split
- **Stratified by target** to preserve class proportions

### 4. Handling Class Imbalance
- Used **RandomOverSampler**
- Implemented inside an **imblearn Pipeline**
- Prevented data leakage during cross-validation

---

## 🤖 Models Trained

### Baseline
- Majority-class classifier
- Accuracy ≈ 95%
- Recall (bankrupt) = 0.00

### Decision Tree
- Shallow tree (`max_depth = 5`)
- Improved recall but unstable

### ✅ Random Forest (Final Model)

**Best hyperparameters:**
- `n_estimators = 300`
- `max_depth = 20`
- `min_samples_leaf = 10`
- `max_features = sqrt`

---

## 📈 Evaluation Strategy
- **Primary metric:** Recall (Bankrupt class)
- **Secondary metrics:** Precision, F1-score, ROC-AUC

---

## 🎚️ Threshold Tuning

**Final threshold:** `0.30`

### Final Confusion Matrix (Test Set)

|                | Predicted Non-Bankrupt | Predicted Bankrupt |
|----------------|------------------------|--------------------|
| Actual Non-Bankrupt | 1765 | 138 |
| Actual Bankrupt     | 45   | 48  |

### Final Performance

| Metric | Value |
|------|------|
| Recall (Bankrupt) | **0.52** |
| Precision (Bankrupt) | 0.26 |
| F1-score | 0.34 |
| Accuracy | 0.91 |

---

## 🧾 Key Insights
- Accuracy is misleading for imbalanced problems
- Oversampling must be applied inside cross-validation
- Threshold tuning is essential for deployment

---

## ⚠️ Limitations
- Low precision due to screening objective
- Oversampling may inflate minority patterns
- Model is not a final decision system

---

## 🔮 Future Work
- SMOTE or hybrid resampling
- Gradient boosting (XGBoost, LightGBM)
- Probability calibration
- Cost-sensitive learning

---

## 🛠️ Tech Stack
- Python
- pandas, numpy
- scikit-learn
- imbalanced-learn
- matplotlib, seaborn


---

## ✅ Final Verdict
This project demonstrates strong handling of imbalanced data, correct evaluation methodology, and business-aware ML decision-making.


