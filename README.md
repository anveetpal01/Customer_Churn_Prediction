# 📊 Customer Churn Prediction

## 🧠 Problem

Telecom companies lose revenue when customers stop using their services (churn).
The goal of this project is to predict which customers are likely to churn so the company can take proactive retention actions.

---

## 📁 Dataset

* Size: ~440k rows
* Features: Customer demographics, usage behavior, payment patterns
* Target: `Churn` (1 = churn, 0 = stay)

---

## ⚙️ Approach

* Exploratory Data Analysis (EDA)
* Data preprocessing (cleaning, encoding, scaling)
* Baseline model (Logistic Regression)
* Advanced models (Random Forest, XGBoost)
* Model evaluation (F1, ROC-AUC, Precision-Recall)
* Explainability using SHAP

---

## 📊 Key Insights (EDA)

* Customers with **low tenure** have significantly higher churn rates
* High number of **support calls** indicates dissatisfaction → churn
* **Payment delays** strongly correlate with churn
* Customers with **low usage frequency** are more likely to leave
* **Short contract lengths** lead to higher churn

*(See charts in **`/reports/figures/`**)*

---

## 🤖 Model Performance

| Model               | Accuracy | Precision | Recall  | F1 Score | ROC-AUC  |   |   |   |
| ------------------- | -------- | --------- | ------- | -------- | -------- | - | - | - |
| Logistic Regression | 0.894563 | 0.924832  | 0.88610 | 0.905052 | 0.959754 |   |   |   |
| Random Forest       | 0.999342 | 0.999920  | 0.99892 | 0.999420 | 0.999998 |   |   |   |
| XGBoost ⭐           | 0.999898 | 0.999980  | 0.99984 | 0.999910 | 0.999994 |   |   |   |

👉 **Final Model: XGBoost** (best balance of recall & precision)

---

## 📈 Evaluation Strategy

* Dataset is imbalanced → accuracy is misleading
* Focus on:

  * **Recall** → catch maximum churners
  * **F1 Score** → balance precision & recall
  * **ROC-AUC** → overall model quality

---

## 🔍 Explainability (SHAP)

* **Tenure** and **Support Calls** are strongest predictors
* Customers with:

  * low tenure
  * high support calls
  * payment delays
    → have highest churn probability

---

## 💰 Business Impact

* Early identification of churn-prone customers
* Targeted retention campaigns (discounts, support improvements)
* Reduced revenue loss

👉 Example:
If retention cost = $50 and customer value = $500
→ even 10% precision is profitable

---

## 🚀 How to Run

```bash
git clone https://github.com/your-username/telco-churn-prediction.git
cd telco-churn-prediction
pip install -r requirements.txt
jupyter notebook
```

---

## 🔮 Future Improvements

* Deploy model using Flask / FastAPI
* Real-time churn prediction system
* A/B testing for retention strategies
* Model monitoring (drift detection)

---
