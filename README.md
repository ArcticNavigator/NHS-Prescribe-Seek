# NHS Prescribe-Seek - NHS Primary Care Prescribing Analysis & Overspending Prediction (2025)

**An end-to-end data science project that analyses £10.54 billion of NHS primary care prescribing across 217 million records, finds where the NHS overspends, and predicts which GP practices will exceed their expected costs before the money is spent.**

[![Live Dashboard](https://img.shields.io/badge/Live-Dashboard-20B2AA?style=for-the-badge)](https://nhs-prescribing-dashboard.onrender.com)
[![Live Model App](https://img.shields.io/badge/Live-Prediction%20App-7B68EE?style=for-the-badge)](https://nhs-prescribing-model-ah5jesmyr8b6y6gbeqzah5.streamlit.app)
[![Python](https://img.shields.io/badge/Python-3.13-blue?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-App-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://streamlit.io)

---

## What is this project?

NHS Prescribe-Seek is a complete analytics case study on **NHS primary care prescribing in England for 2025**. It takes the raw NHS Business Services Authority (NHSBSA) English Prescribing Dataset (EPD SNOMED), cleans and combines 12 months of data into a single 217-million-row dataset, and answers one business question:

> **Where is the NHS overspending on primary care prescribing, and can we predict which GP practices will go over budget before it happens?**

The project covers the full data science workflow end to end, data engineering, exploratory data analysis, machine learning, time-series forecasting, and deployment of two live web applications.

This is the **main repository** containing the complete project: the analysis notebook, the dashboard, and the prediction model. Two parts are also deployed as standalone live apps (see below).

---

## Live applications

| App | What it does | Link |
|-----|--------------|------|
| **Interactive Dashboard** | Explore all findings across 8 chapters, cost, geography, overspending, prediction, forecasting and seasonality | [nhs-prescribing-dashboard.onrender.com](https://nhs-prescribing-dashboard.onrender.com) |
| **Overspending Predictor** | Upload a real NHSBSA prescribing file and get a ranked list of at-risk GP practices | [Open the model app](https://nhs-prescribing-model-ah5jesmyr8b6y6gbeqzah5.streamlit.app) |

> Note: the dashboard runs on a free hosting tier and may take 30–60 seconds to wake up on the first visit.

---

## Headline findings

- The NHS spent **£10.54 billion** on primary care prescribing in 2025 across **1.27 billion** prescriptions.
- The **Endocrine System** is the most expensive drug category (£2.23B, 21% of all spend) yet only the 3rd most prescribed — cost is driven by drug pricing, not volume.
- The **Cardiovascular System** is the most prescribed category (388 million items, 30.6% of all prescriptions) but only 4th in cost, because most of its drugs are cheap generics.
- **NHS Hampshire and Isle of Wight** is the most expensive Integrated Care Board (ICB) at £22.14 per prescription; **NHS North West London** is the cheapest at £18.04 - a persistent £4.10 gap every month.
- **288 GP practices** overspend every single month relative to their local peers; the analysis proves this is driven by prescribing behaviour, not procurement prices or patient volume.
- A **Random Forest model** predicts practice-level prescribing cost with **95.4% accuracy (R² = 0.954)** and flags **2,417 at-risk practices** for early intervention.

---

## Tech stack

- **Python** - core analysis language
- **DuckDB** - fast SQL queries over 217 million rows without loading them into memory
- **pandas** - data wrangling
- **scikit-learn** - Random Forest, Gradient Boosting, Linear Regression
- **statsmodels** - seasonal decomposition for time-series analysis
- **Plotly** - interactive charts and maps
- **GeoPandas** - geographic ICB mapping
- **Streamlit** - both web applications
- **Render** and **Streamlit Community Cloud** - hosting

---

## How the analysis is structured

The project runs across seven chapters, each building on the last:

- **Chapter 0 - Building the data.** Combine and clean 12 monthly files into one 217-million-row dataset.
- **Chapter 1 - What is the NHS prescribing?** Find which drug categories cost the most versus which are prescribed the most.
- **Chapter 2 - Where is the money going?** Compare cost per prescription across 42 ICBs and 7 regions.
- **Chapter 3 - Who is overspending?** Identify individual GP practices that spend more than their local peers, month after month.
- **Chapter 4 - Can we predict overspending?** Build a Random Forest model to flag at-risk practices before they go over budget.
- **Chapter 5 - Can we forecast spikes?** Forecast November and December spending for high-risk drug categories.
- **Chapter 6 - Does time of year explain spikes?** Measure which categories are seasonal and whether seasonality differs by region.

---

## Repository structure

```
NHS-Prescribe-Seek/
├── notebook/          # Full analysis notebook (Chapters 0–6)
├── Dashboard/         # Streamlit dashboard and pre-computed summary data
├── NHS_Model/         # Random Forest model and prediction app
└── README.md
```

---

## Related repositories

This main repository links two standalone deployments:

- **Dashboard repository** → [NHS-prescribing-dashboard](https://github.com/ArcticNavigator/NHS-prescribing-dashboard) (hosted on Render)
- **Model repository** → [NHS-prescribing-model](https://github.com/ArcticNavigator/NHS-prescribing-model) (hosted on Streamlit Cloud)

---

## Run it locally

```bash
# Clone the repository
git clone https://github.com/ArcticNavigator/NHS-Prescribe-Seek.git
cd NHS-Prescribe-Seek

# Install dependencies
pip install -r requirements.txt

# Run the dashboard
streamlit run Dashboard/dashboard.py

# Or run the model app
streamlit run NHS_Model/model_app.py
```

---

## Data source

English Prescribing Dataset (EPD) with SNOMED code - NHS Business Services Authority Open Data Portal: https://opendata.nhsbsa.net/dataset/english-prescribing-dataset-epd-with-snomed-code

---

## Author

Built by **ArcticNavigator**.

---

*Keywords: NHS prescribing analysis, NHS primary care prescribing, healthcare data science, NHS overspending prediction, GP practice prescribing costs, Random Forest healthcare model, NHS EPD SNOMED dataset, DuckDB big data, Streamlit healthcare dashboard, predictive analytics NHS, ICB prescribing comparison, NHS data visualisation, machine learning healthcare England.*
