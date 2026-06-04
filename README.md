# Motor-Insurance-Churn-Prediction
End-to-end Machine Learning pipeline to predict customer churn in the motor insurance sector (LightGBM).

> **Project developed during the Master in Data Science at Bologna Business School, in collaboration with Var Group.**

## 📖 Business Context
An Italian insurance company operating primarily in the automotive market seeks to improve client retention rates. The strategic priority is to identify customers at the highest risk of leaving before contract renewal. By developing a predictive anti-churn model, the company aims to enable proactive customer management and significantly reduce contract non-renewal rates (historically around ~21.5%).

## 🎯 Project Objective
Develop a predictive model estimating churn probability within one year to enable proactive retention strategies. The strategic goal is to prioritize retention efforts on high-risk customers, optimizing campaign resources and maximizing customer lifetime value.

## 📁 Repository Structure
- `ML_Churn_Project_Contract_Level.ipynb`: The complete Python notebook containing data extraction, cleaning, feature engineering, and model training/evaluation.
- `Predicting Churn in Italian Motor Insurance.pdf`: Executive presentation detailing the business problem, insights, and actionable retention strategies.

> ⚠️ **Note:** Original datasets are not included in this repository to strictly comply with company privacy guidelines and Non-Disclosure Agreements (NDA).

## 🧠 Approach & Feature Engineering
I developed an independent, client-centric analytical pipeline focusing on the chronological history of individual customers to prevent right-censoring data leakage.

* **Business-Logic Imputation:** Handled missing values using domain knowledge (e.g., classifying 80% missing values in installment payments as upfront one-off payments rather than lost data).
* **Chronological Target Engineering:** Defined "Churn" using a strict 365-day tolerance window from policy expiration.
* **Advanced Features:** Created custom metrics like *Price Shock* (year-over-year premium deltas), *Active Coverage Loyalty*, and *Claims-per-Year* ratios.

## ⚙️ Modeling & Results
Multiple models were tested to handle the severe class imbalance, including Logistic Regression, Random Forest, CatBoost, and XGBoost. **LightGBM** emerged as the absolute champion.

### 🏆 Model Performance (LightGBM)
* **ROC-AUC:** `88.7%` (Excellent ranking ability)
* **Recall:** `93.6%` (Successfully intercepted 94 out of 100 potential churners)

### 💡 Key Business Insights
1. Clients with **zero optional coverages** are nearly **3x more likely to churn**. 
2. **New clients** (0-1 year) and **mid-tenure clients** (4-7 years) represent the highest risk segments.

## 🛠️ Tools & Technologies Used
* **Language:** Python
* **Data Handling:** `pandas`, `numpy`
* **Machine Learning:** `scikit-learn`, `LightGBM`, `XGBoost`, `CatBoost`
* **Data Visualization:** `matplotlib`, `seaborn`
