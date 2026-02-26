# subscriber-churn-analysis
Identify why users leave and provide evidence-based actions to stabilize the subscriber base
Love this direction—this is exactly how you turn a solid analysis into a **hire-me-now portfolio repo** 💼✨
Below is a **drop-in upgrade** to your existing README. You can paste these sections straight into your `README.md`.

---

## 📂 Project Structure

```text
subscriber-churn-analysis/
│
├── data/
│   ├── raw/
│   │   └── subscriber_data_raw.csv
│   ├── processed/
│   │   └── subscriber_data_clean.csv
│
├── notebooks/
│   ├── 01_data_cleaning_validation.ipynb
│   ├── 02_exploratory_data_analysis.ipynb
│   ├── 03_feature_engineering.ipynb
│   └── 04_churn_modeling.ipynb
│
├── dashboards/
│   ├── churn_overview.pbix
│   └── churn_overview.html
│
├── sql/
│   └── churn_analysis_queries.sql
│
├── reports/
│   └── churn_analysis_summary.pdf
│
├── README.md
└── requirements.txt
```

📌 **Why this matters:**
Recruiters immediately see **organization, reproducibility, and real-world workflow**.

---

## 📊 Visual Insights & Key Figures

> *All figures were generated using Python (Matplotlib / Seaborn) and Power BI.*

### Figure 1: Overall Churn Rate

![Overall Churn Rate](assets/figures/overall_churn_rate.png)

📌 Shows that nearly **33% of users churn**, highlighting the urgency of retention efforts.

---

### Figure 2: Churn by Subscription Tier

![Churn by Tier](assets/figures/churn_by_tier.png)

📌 Free-tier users churn almost **2× more** than Pro users, confirming value perception issues.

---

### Figure 3: Engagement vs Churn (AER)

![AER vs Churn](assets/figures/aer_vs_churn.png)

📌 Users with **AER < 0.5** are significantly more likely to churn.

---

### Figure 4: Support Tickets Distribution

![Support Tickets](assets/figures/support_volume.png)

📌 Support volume is similar for churned and retained users—**support quality is not the main driver**.

---

## 🧪 Model Training & Evaluation

### Objective

Predict whether a subscriber is likely to churn based on **engagement, subscription tier, and support interactions**.

---

### Feature Engineering

Key features created:

* `active_engagement_rate (AER)`
* `subscription_tier_encoded`
* `support_ticket_count`
* `days_since_last_activity`
* `account_age_days`

---

### Models Used

| Model               | Purpose                           |
| ------------------- | --------------------------------- |
| Logistic Regression | Baseline & interpretability       |
| Random Forest       | Capture non-linear churn patterns |
| XGBoost (optional)  | Performance optimization          |

---

### Evaluation Metrics

* **Accuracy**
* **Precision / Recall**
* **F1-Score**
* **ROC-AUC**

📌 **Business focus:** Recall was prioritized to avoid missing at-risk users.

---

### Sample Results (Illustrative)

| Model               | ROC-AUC  | Recall   |
| ------------------- | -------- | -------- |
| Logistic Regression | 0.74     | 0.68     |
| Random Forest       | **0.82** | **0.77** |

📌 **Top Predictor:** Active Engagement Rate (AER)

---

## 🧠 SQL Analysis Highlights

Example queries used to support analysis:

```sql
-- Churn rate by subscription tier
SELECT
    subscription_tier,
    COUNT(*) AS total_users,
    SUM(CASE WHEN churn_status = 'Churned' THEN 1 ELSE 0 END) * 1.0 / COUNT(*) AS churn_rate
FROM subscribers
GROUP BY subscription_tier;
```

📌 Demonstrates ability to perform **production-ready analysis directly in SQL**.

---

## 🎯 Recruiter & Hiring Manager Highlights

✅ End-to-end analytics project
✅ Business framing, not just charts
✅ Data cleaning & validation at scale
✅ KPI design (leading indicators)
✅ SQL + Python + BI dashboards
✅ Actionable recommendations tied to revenue

> *This project mirrors real-world analytics work in subscription-based and SaaS businesses.*

---

## 💼 Ideal Roles This Project Targets

* Data Analyst
* Business Intelligence Analyst
* Product Analyst
* Operations / Strategy Analyst
* Junior Data Scientist

---

## 🚀 How to Run This Project Locally

```bash
git clone https://github.com/SyusufWaliyyi/subscriber-churn-analysis.git
cd subscriber-churn-analysis
pip install -r requirements.txt
jupyter notebook
```
