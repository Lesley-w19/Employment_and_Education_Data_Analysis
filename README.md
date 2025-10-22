# Employment & Education Data Analysis in Canada  
*Exploring the link between education and employment outcomes using Statistics Canada data*  

---

## 🎯 Project Overview
This project investigates how **education level** influences **employment outcomes** in Canada using official **Statistics Canada Labour Force data**.  
It combines **Python**, **Excel**, and **Power BI** to deliver a full analytical workflow — from data cleaning and statistical analysis to dashboard reporting.

**Objectives:**
- Clean and analyze national and provincial labor force data.
- Identify correlations between education level and employment rate.
- Build an interactive Power BI dashboard for visual exploration and policy insights.

---

## 🧰 Tools & Technologies
| Tool | Purpose |
|------|----------|
| **Python (Pandas, Matplotlib)** | Data cleaning, exploration, and correlation analysis |
| **Excel** | Data validation and tabular exploration |
| **Power BI Desktop** | Dashboarding and policy insight visualization |
| **Statistics Canada WDS API** | Live data retrieval |

---

## 📦 Data Sources
| Table ID | Title | Description |
|-----------|--------|-------------|
| **14-10-0118-01** | Labour force characteristics by educational degree (annual) | Main dataset used for national-level analysis |
| **14-10-0019-01** | Labour force characteristics by educational attainment (monthly) | Supplementary for trend insights |
| **98-10-0400-01** | Census: Labour force status by highest level of education | Provincial-level distribution |

> Data is sourced from Statistics Canada’s Web Data Service (WDS): https://www.statcan.gc.ca/en/developers/wds

---

## 🧮 Data Analysis Summary (Python)
- **Step 1:** Data Cleaning → removed duplicates, standardized labels.  
- **Step 2:** Exploratory Data Analysis → trends by year and education level.  
- **Step 3:** Correlation → mapped education to ordinal scale (1–5).  
- **Step 4:** Regression & Visualization → linear trends between education level and employment rate.  

**Key Insight:**  
> Across 2015–2025, higher education consistently correlates with higher employment rates.  
> Pearson correlation (education vs employment rate): **≈ +0.86**, indicating a strong positive relationship.  

---

## 🧭 Power BI Dashboard Layout

### 1️⃣ Page 1: *National Overview*
**Visuals:**
- **Clustered Column Chart:** Employment Rate (%) by Education (Year slicer).  
- **Line Chart:** Trend of Employment Rate over Time by Education.  
- **Card KPIs:**  
  - Avg Employment Rate  
  - Avg Participation Rate  
  - Avg Unemployment Rate  

### 2️⃣ Page 2: *Provincial Comparison*
**Visuals:**
- **Map Visual:** Employment Rate by Province (color-coded).  
- **Stacked Column Chart:** Employment vs Unemployment by Education per Province.  
- **Slicer:** Year, Education.  

### 3️⃣ Page 3: *Insight & Trends*
**Visuals:**
- **Scatter Plot:** Participation vs Employment Rate (Education as legend).  
- **Decomposition Tree:** Explore factors influencing Employment Rate.  
- **Tooltip Page:** Displays KPIs for selected province/year.

### 4️⃣ Page 4: *Forecasts & What-If*
**Visuals:**
- **Line Forecast:** Future trend projection using Power BI’s Analytics Pane.  
- **What-If Parameter:** Education index slider to simulate future employment rate.  

---

## 📊 Suggested DAX Measures
```DAX
Avg Employment Rate = AVERAGE('LabourForce'[employment_rate])

Employment YoY Change = 
VAR PrevYear = CALCULATE(AVERAGE('LabourForce'[employment_rate]), 
                DATEADD('LabourForce'[ref_date], -1, YEAR))
RETURN AVERAGE('LabourForce'[employment_rate]) - PrevYear

Participation_to_Employment = 
DIVIDE(AVERAGE('LabourForce'[employment_rate]), AVERAGE('LabourForce'[participation_rate]))
```

---

## 🖼️ Dashboard Preview Placeholders

| Page | Screenshot |
|------|-------------|
| **National Overview** | ![National Overview Placeholder](images/national_overview.png) |
| **Provincial Comparison** | ![Provincial Placeholder](images/provincial_comparison.png) |
| **Trends and Forecasts** | ![Trends Placeholder](images/trends_forecast.png) |
| **Insights Page** | ![Insights Placeholder](images/insights_page.png) |

*(Upload your Power BI dashboard screenshots here once created.)*

---

## 🧩 Project Structure
```
Employment_Education_Analysis/
├── data/
│   ├── powerbi_employment_education_sample.csv
│   ├── cleaned_employment_education.csv
│   └── Employment_Education_Project.xlsx
├── notebooks/
│   └── employment_education_analysis.ipynb
├── powerbi/
│   ├── Employment_Education_Dashboard.pbix  (to be created in Power BI)
│   ├── POWERBI_README.md
│   └── images/ (dashboard screenshots)
└── README.md
```

---

## 📈 Insights for Interview
> “This project demonstrates end-to-end data storytelling — from sourcing and analyzing official Statistics Canada data to delivering business-ready dashboards.  
The results show that education level is a significant predictor of employment success in Canada, reinforcing the need for targeted upskilling policies.”

---

## 🧠 Next Steps
- Extend to **gender and age-based breakdowns** using additional StatCan tables.  
- Use **ARIMA / Prophet models** for forecasting trends.  
- Deploy dashboard to **Power BI Service** and automate refresh from the WDS API.

---

**Author:** Lesley Wanjiku Kamamo   
**Tools:** Python · Excel · Power BI  
**GitHub:** https://github.com/Lesley-w19
