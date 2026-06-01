# 💼 New Hire Salary vs Inflation vs Loyalty Pay Pipeline

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/webuild262-boop/salary-inflation-loyalty-pipeline/blob/main/salary_loyalty_pipeline.ipynb)
![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Data Source](https://img.shields.io/badge/Data-FRED%20API-orange)
![Model](https://img.shields.io/badge/Model-Random%20Forest-green)
![Live Data](https://img.shields.io/badge/Data-Live%20%7C%20No%20API%20Key-brightgreen)

A 12-step end-to-end ML pipeline that **quantifies the loyalty penalty** — the gap between what companies pay new hires versus how much they raise existing employees — measured against real inflation. Pulls live data from the Federal Reserve (FRED) every run. No API key required.

---

## 🔍 What Is the Loyalty Penalty?

The **loyalty penalty** is the phenomenon where employees who stay at a company receive smaller raises over time than the market pays new hires for the same role. Combined with inflation, this erodes the real purchasing power of long-tenured workers.

**Loyalty Penalty = Market Wage Growth (AHE) − Incumbent Raise Rate (ECI)**

When positive → new hires are gaining faster than loyal employees.
When negative → employees are holding their ground.

---

## 📡 Data Sources (Live — FRED API, No Key Needed)

| Series | FRED ID | Frequency | What It Represents |
|--------|---------|-----------|-------------------|
| Consumer Price Index | `CPIAUCSL` | Monthly | Inflation rate (All Urban Consumers, SA) |
| Avg Hourly Earnings | `AHETPI` | Monthly | Market wage / new hire pay proxy |
| Employment Cost Index | `ECIWAG` | Quarterly | Incumbent employee raise rate |

---

## 🗂️ Pipeline Steps

| Step | Description |
|------|-------------|
| 1 | Install & import libraries |
| 2 | Pull CPI (inflation) from FRED |
| 3 | Pull Average Hourly Earnings (market wages) from FRED |
| 4 | Pull Employment Cost Index (incumbent raises) from FRED |
| 5 | Resample monthly → quarterly & merge all three series |
| 6 | Calculate year-over-year growth rates |
| 7 | Compute Loyalty Penalty Index & classify quarters |
| 8 | Feature engineering (lags, rolling averages, spreads) |
| 9 | Chronological train/test split (80/20) |
| 10 | Train Random Forest classifier |
| 11 | Dashboard: penalty trends, wage comparison, confusion matrix, feature importance |
| 12 | Forecast next quarter — penalty active or not |

---

## 📊 Dashboard Output

- **Loyalty Penalty Index** — filled area chart showing when new hires beat incumbents
- **Market Wages vs Incumbent Raises vs Inflation** — three-line trend comparison
- **Confusion Matrix** — model test-set performance
- **Feature Importance** — top drivers of the penalty signal

---

## 🛠️ Tech Stack

`Python` · `pandas` · `scikit-learn` · `matplotlib` · `requests` · `FRED API` · `Random Forest`

---

## 🚀 Run It

```bash
# Clone
git clone https://github.com/webuild262-boop/salary-inflation-loyalty-pipeline.git
cd salary-inflation-loyalty-pipeline

# Install
pip install -r requirements.txt

# Run in Jupyter or click the Colab badge above
jupyter notebook salary_loyalty_pipeline.ipynb
```

Or click **Open in Colab** at the top — no setup needed.

---

## 👤 Author

**Allen Ramirez** · [LinkedIn](https://www.linkedin.com/in/allen-ramirez-) · [GitHub](https://github.com/webuild262-boop)

