# Customer Segmentation of Credit-Fearful Households (US)

## Project Overview

This project performs **customer segmentation** on U.S. households using data from the **Survey of Consumer Finances (SCF 2019)**.  
The analysis focuses specifically on **credit-fearful households**—those that avoided borrowing due to fear or uncertainty.

The goal is to:
- Understand the demographic and financial characteristics of credit-fearful households
- Segment these households into meaningful clusters using **KMeans**
- Provide interpretable cluster profiles based on financial behavior

This project is implemented using **two Jupyter notebooks**:
1. Exploratory Data Analysis (EDA)
2. KMeans clustering and PCA visualization

---

## Data Source

- **Dataset:** Survey of Consumer Finances (SCF) 2019  
- **Provider:** U.S. Federal Reserve  
- **File used:** `SCFP2019.csv.gz`

The SCF is a triennial survey that provides detailed information on U.S. household finances, including income, assets, debts, and demographic variables.

---

## Project Structure

```
customer_segmentation_us/
│
├── data/
│   └── SCFP2019.csv.gz
│
├── notebooks/
│   ├── 01_eda_customer_segmentation.ipynb
│   └── 02_kmeans_customer_segmentation.ipynb
│
├── requirements.txt
└── README.md
```

---

## Notebook 1: Exploratory Data Analysis (EDA)

**File:** `01_eda_customer_segmentation.ipynb`

### Key Tasks
- Filter credit-fearful households (`TURNFEAR == 1`)
- Analyze demographic variables:
  - Age
  - Education
  - Income category
- Explore financial variables:
  - Assets
  - Debt
  - Housing wealth
- Compare distributions between:
  - Credit-fearful vs non-fearful households
- Examine correlations among financial features

### Tools & Techniques
- Pandas for data manipulation
- Matplotlib & Seaborn for visualization
- Distribution analysis and correlation matrices

---

## Notebook 2: KMeans Clustering

**File:** `02_kmeans_customer_segmentation.ipynb`

### Key Tasks
- Data wrangling and outlier removal
- Feature selection using:
  - Variance
  - **Trimmed variance** (robust to outliers)
- Feature scaling with `StandardScaler`
- Model selection using:
  - Inertia (Elbow Method)
  - Silhouette score
- Final KMeans model training
- Cluster profiling using group means
- Dimensionality reduction with PCA for visualization

### Tools & Techniques
- Scikit-learn (`KMeans`, `PCA`, `StandardScaler`)
- Robust statistics (`trimmed_var`)
- Matplotlib for diagnostic plots

---

## Key Results

- Credit-fearful households can be meaningfully segmented based on financial behavior
- Clusters differ significantly in:
  - Asset ownership
  - Debt levels
  - Income and education
- PCA visualization confirms separation between clusters
- Variance-based feature selection improves clustering stability

---

## Installation & Setup

### 1. Clone the repository
```bash
git clone https://github.com/your-username/customer-segmentation-us.git
cd customer-segmentation-us
```

### 2. Create a virtual environment (recommended)
```bash
python -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\activate      # Windows
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

---

## Requirements

```
numpy
pandas
matplotlib
seaborn
scikit-learn
scipy
```

---

## Notes

- This project focuses on **analysis and modeling**, not deployment
- A dashboard or web app can be added in the future using the clustering outputs
- The notebooks are designed to be **reproducible and modular**

---

## Author

**Ahmed Khalil**  
Aspiring Data Scientist / Machine Learning Engineer

---

## License

This project is for **educational and portfolio purposes**.
