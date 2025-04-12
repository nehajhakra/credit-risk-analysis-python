# 💳 Credit Risk Analysis Using Python 🐍

Welcome to my Data Analytics project focused on identifying and analyzing **credit risk** using Python. This end-to-end notebook showcases real-world techniques like merging datasets, calculating statistical summaries, applying rule-based risk classification, and visualizing patterns — all in Python!

---

## 📌 Objective

The aim of this project is to:

- Identify **High**, **Medium**, and **Low** risk customers
- Understand how **loan amounts** vary across **loan types**
- Perform **statistical analysis** and uncover hidden patterns
- Build a strong **data storytelling** foundation for further dashboarding (Power BI coming soon!)

---

## 📂 Dataset Overview

This project uses two CSV files:

- `customers_medium.csv` — includes customer demographics and income
- `loans_medium.csv` — includes loan amount, type, credit score, etc.

---

## 🔄 Steps Performed

### 1️⃣ Data Loading & Merging
```python
customers = pd.read_csv('customers_medium.csv')
loans = pd.read_csv('loans_medium.csv')
merged_data = pd.merge(customers, loans, on='customer_id', how='left')

2️⃣ Risk Classification Logic
merged_data['risk'] = merged_data.apply(
    lambda x: 'High' if x['credit_score'] < 600 and x['loan_amount'] > 100000
    else 'Medium' if x['credit_score'] < 700
    else 'Low',
    axis=1
)
3️⃣ Visual Insights
Pie Chart: Risk Distribution
Bar Charts: Number & Avg Loan by Loan Type
Regression Plot: Income vs Loan Amount
Histogram: Loan Amount Distribution

4️⃣ Descriptive & Statistical Analysis
mean, median, mode, std, skewness
Correlation (Pearson) between income and loan amount
ANOVA to check variance across loan types

📊 Key Takeaways
Loan amount distribution is right-skewed
Customers with lower credit scores & high loans are high risk
Strong positive correlation between income & loan amount
Loan types significantly impact average loan amounts (ANOVA p < 0.05)

🛠️ Tools & Libraries
Python (Pandas, NumPy)
Seaborn & Matplotlib
SciPy (for statistical testing)

📌 How to Use
git clone https://github.com/your-username/credit-risk-analysis-python.git
cd credit-risk-analysis-python
pip install -r requirements.txt

⭐ Credits
Made with ❤️ by Neha Jhakra
📫 Connect on LinkedIn



