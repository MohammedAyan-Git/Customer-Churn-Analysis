# Customer Churn Analysis (Telco Dataset)

An exploratory data analysis (EDA) of a telecom customer dataset to find out **who churns and why**, with a focus on contract type, payment method, tenure, internet services and senior-citizen status. The findings are turned into practical retention recommendations.

## Project Overview

Customer churn directly hurts recurring revenue, and keeping an existing customer is usually cheaper than acquiring a new one. This project analyses customer records to answer:

- What share of customers churn overall?
- Which **contract types** and **payment methods** are linked to higher churn?
- How does churn change with **customer tenure**?
- Do **internet service type** and **add-on services** (security, backup, tech support, etc.) affect churn?
- Are **senior citizens** more likely to leave?

## Dataset

| Property | Detail |
|---|---|
| Source | Telco Customer Churn dataset (publicly available, e.g. on Kaggle) |
| Rows | 7,043 customers |
| Columns | 21 |
| Target | `Churn` (Yes / No) |

**Feature groups**
- **Demographics:** `gender`, `SeniorCitizen`, `Partner`, `Dependents`
- **Account info:** `tenure`, `Contract`, `PaperlessBilling`, `PaymentMethod`, `MonthlyCharges`, `TotalCharges`
- **Services:** `PhoneService`, `MultipleLines`, `InternetService`, `OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`, `StreamingTV`, `StreamingMovies`

- <a href="https://github.com/MohammedAyan-Git/Customer-Churn-Analysis/blob/main/Customer_Churn_Dataset.csv">Customer_Churn_Dataset</a>

## Tools & Libraries

- **Python 3**
- **Pandas** – data loading, cleaning, aggregation
- **NumPy** – numerical operations
- **Matplotlib & Seaborn** – visualization
- **Jupyter Notebook** – analysis environment

## Data Preparation

1. Loaded the dataset and inspected structure with `df.info()` and `df.describe()`.
2. Fixed `TotalCharges`: it was stored as text because of blank values. Blanks were replaced with `0` and the column converted to `float`.
3. Checked data quality: **0 null values** and **0 duplicate rows** (including duplicate `customerID`s).
4. Converted `SeniorCitizen` from `0/1` to `no/yes` so it reads clearly in charts.

**Quick profile:** average tenure ≈ 32 months (max 72), average monthly charge ≈ 64.76, and about 16% of customers are senior citizens.

## Key Findings

**Overall churn: 26.54%** of customers churned and 73.46% stayed.

| Factor | Finding |
|---|---|
| **Contract type** | Month-to-month customers churn far more (≈ 43%) than one-year (≈ 11%) and two-year (≈ 3%) customers. Longer commitments strongly protect retention. |
| **Payment method** | Electronic check users churn the most: **≈ 45%** (1,071 of 2,365). Other methods are much lower: mailed check ≈ 19%, bank transfer (automatic) ≈ 17%, credit card (automatic) ≈ 15%. |
| **Tenure** | Churn is concentrated among new customers (the first few months). Long-tenured customers rarely leave. |
| **Internet service** | Fiber optic users show the highest churn among internet service types. Customers with no internet service churn very little. |
| **Add-on services** | Customers **without** Online Security, Online Backup, Device Protection or Tech Support churn noticeably more than those who have them. |
| **Senior citizens** | **41.7%** of senior citizens churned vs **23.6%** of non-seniors. |

## Visualizations

### Overall churn rate
![Churn rate](https://github.com/MohammedAyan-Git/Customer-Churn-Analysis/blob/main/churn_rate_pie.png)

### Churn by contract type
![Churn by contract](https://github.com/MohammedAyan-Git/Customer-Churn-Analysis/blob/main/churn_by_contract.png))

### Churn by payment method
![Churn by payment method](https://github.com/MohammedAyan-Git/Customer-Churn-Analysis/blob/main/churn_by_payment_method.png)

### Tenure vs churn
![Tenure vs churn](https://github.com/MohammedAyan-Git/Customer-Churn-Analysis/blob/main/tenure_vs_churn.png)

### Churn by senior citizen status
![Churn by senior citizen](https://github.com/MohammedAyan-Git/Customer-Churn-Analysis/blob/main/churn_by_senior_citizen.png)

### Services vs churn
![Services vs churn](https://github.com/MohammedAyan-Git/Customer-Churn-Analysis/blob/main/services_vs_churn.png)

## Recommendations

1. **Promote longer contracts:** offer discounts or perks to move month-to-month customers onto one- or two-year plans.
2. **Move customers off electronic check:** encourage automatic payments (bank transfer or credit card) through incentives or small bill credits, and investigate friction in the electronic-check experience.
3. **Invest in early-tenure engagement:** run onboarding, check-ins and loyalty offers during the first months, when churn risk is highest.
4. **Bundle protective add-ons:** offer Online Security, Backup, Device Protection and Tech Support as trials or bundles, since customers with them churn less.
5. **Review fiber optic service quality and pricing:** investigate reliability, speed and competitor offers behind the higher churn.
6. **Create a senior-focused retention program:** simplified plans, dedicated support and personalized outreach.

## How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/MohammedAyan-Git/<your-repo-name>.git
   cd <your-repo-name>
   ```
2. **Install dependencies**
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```
3. **Add the dataset** as `Customer_Churn_Dataset.csv` in the project folder.
4. **Update the file path** in the notebook's data-loading cell, for example:
   ```python
   df = pd.read_csv("Customer_Churn_Dataset.csv")
   ```
5. **Launch the notebook**
   ```bash
   jupyter notebook Churn_Analysis.ipynb
   ```

## Future Improvements

- Build a predictive model (Logistic Regression, Random Forest, XGBoost) to score churn risk per customer.
- Add a Power BI / Tableau dashboard for interactive exploration.
- Segment customers (e.g., by tenure and monthly charges) and estimate revenue at risk.
- Test the statistical significance of the differences between groups.

## Author

**Mohammed Ayan**
[Connect with me on LinkedIn](https://www.linkedin.com/in/mohammedayan-in/)
