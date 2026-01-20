# Earthquake Damage Prediction in Nepal

## Overview
This project applies machine learning techniques to predict **severe building damage** following an earthquake using **pre-event structural and demographic features**. The goal is to support data-driven decision-making for disaster preparedness and post-earthquake response.

The analysis is based on relational data extracted from a SQLite database containing building characteristics and observed damage outcomes from the Nepal earthquake.

---

## Problem Statement
Given pre-earthquake building attributes, can we accurately predict whether a building will suffer **severe structural damage** during an earthquake?

This task is formulated as a **binary classification problem**, where severe damage is derived from observed damage grades.

---

## Dataset
- **Source:** SQLite relational database
- **Geographic Scope:** Selected district in Nepal
- **Key Tables:**
  - Building structure information
  - Damage assessment records
  - Building ID mappings

Only **pre-earthquake features** are used to avoid data leakage.

---

## Methodology

### Data Extraction
- Data retrieved via SQL queries joining multiple relational tables
- Each building uniquely indexed to preserve data integrity

### Data Wrangling and Feature Engineering
- Removal of post-earthquake variables to prevent leakage
- Target engineering to create a binary outcome:
  - `1` → Severe damage
  - `0` → Non-severe damage
- Removal of redundant and highly correlated features

### Model Selection Rationale
Multiple classification models were evaluated to balance interpretability and predictive performance:
- **Logistic Regression** as a simple, interpretable baseline
- **Decision Tree Classifier** to capture non-linear feature interactions

Pipelines were used to ensure consistent preprocessing and fair model comparison.

### Evaluation
- Models evaluated using accuracy on a held-out test set
- Performance compared to assess trade-offs between simplicity and predictive power

---

## Results
Tree-based model demonstrated improved performance in capturing non-linear relationships in structural data, while Logistic Regression provided a strong and interpretable baseline.

---

## Author

- Ahmed Khalil

