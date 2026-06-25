# Telco Customer Churn Analysis

An end-to-end data analytics project analysing customer churn for a telecommunications company. The project covers data cleaning, exploratory data analysis (EDA) in Python, and an interactive dashboard built in Power BI.

---

##  Project Structure

```
├── telco_churn_analysis.ipynb   # Python notebook: data cleaning, EDA & visualisations
├── clean_telco.csv              # Cleaned dataset exported from Python
├── telco dashboard.pbix         # Power BI dashboard file
└── README.md
```

---

##  Objective

To identify the key drivers of customer churn and surface actionable insights through visual analysis — helping the business understand which customer segments are most at risk.

---

##  Dataset

**Source:** [IBM Watson Telco Customer Churn Dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

- 7,043 customer records
- 21 columns covering demographics, services subscribed, contract details, and churn status
- Target variable: `Churn` (Yes / No)

---

## 🔧 Tools & Technologies

| Tool | Purpose |
|---|---|
| Python (Google Colab) | Data cleaning, EDA, visualisations |
| Pandas | Data manipulation |
| Matplotlib & Seaborn | Static visualisations |
| Power BI | Interactive dashboard |
| GitHub | Version control & project documentation |

---

##  Data Cleaning

Key cleaning steps performed in Python:

- **Fixed `TotalCharges` column** — stored as object due to blank strings for new customers (tenure = 0); converted to numeric and filled with 0
- **Created `ChurnFlag`** — numeric encoding of the target variable (Yes = 1, No = 0) for aggregation
- **Created `SeniorCitizenLabel`** — converted 0/1 to readable "Non-Senior" / "Senior" labels
- **Created `TenureBucket`** — grouped continuous tenure into four bands: 0–12 mo, 13–24 mo, 25–48 mo, 49–72 mo
- No duplicate rows found in the dataset

---

##  Key Findings

| Insight | Detail |
|---|---|
| Overall churn rate | **26.5%** of customers churned |
| Highest churn by contract | Month-to-month contracts churn at **~43%** vs 1% for two-year contracts |
| Highest churn by service | Fiber optic customers churn significantly more than DSL customers |
| Highest churn by tenure | New customers (0–12 months) are most likely to churn |
| Highest churn by payment | Electronic check users have the highest churn rate |
| Senior citizens | Churn at a higher rate than non-senior customers |
| Paperless billing | Customers on paperless billing churn more than those on paper billing |
| Add-on services | Customers without OnlineSecurity and TechSupport churn at much higher rates |

---

##  Visualisations (Python)

The notebook includes the following charts:

- Churn distribution (donut chart)
- Churn rate by contract type
- Churn rate by internet service
- Churn rate by payment method
- Churn rate by tenure bucket
- Monthly charges distribution — churned vs retained
- Tenure distribution — churned vs retained
- Churn rate by senior citizen status
- Churn rate by paperless billing
- Churn rate by add-on service subscription

---

##  Power BI Dashboard

The Power BI dashboard (`telco dashboard.pbix`) includes:

- **KPI cards** — Total Customers, Total Churned, Churn Rate, Avg Monthly Charge
- **Bar charts** — Churn rate broken down by contract, internet service, payment method, tenure bucket, senior citizen status, and paperless billing
- **Donut chart** — Overall churn split

DAX measures used:
```
Churn Rate = DIVIDE(SUM(clean_telco[ChurnFlag]), COUNTROWS(clean_telco))
Total Customers = COUNTROWS(clean_telco)
Total Churned = SUM(clean_telco[ChurnFlag])
Avg Monthly Charge = AVERAGE(clean_telco[MonthlyCharges])
```

---

##  How to Run

**Python Notebook:**
1. Upload `WA_Fn-UseC_-Telco-Customer-Churn.csv` to Google Colab
2. Open and run `telco_churn_analysis.ipynb` cell by cell
3. The cleaned dataset will be saved as `clean_telco.csv`

**Power BI Dashboard:**
1. Download `telco dashboard.pbix`
2. Open in Power BI Desktop
3. If prompted, re-link the data source to your local copy of `clean_telco.csv`

---

##  Author

**Naomi Sirya**
[GitHub](https://github.com/umiSirya)
