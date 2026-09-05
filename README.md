# Seasonal-Agriculture-Performance-Analysis
<div align="center">

# 🌾 Seasonal Agriculture Performance Analysis

**Investigating how Indian cropping seasons — Kharif, Rabi & Zaid — shape yield, resource use, and farm economics**

![Python](https://img.shields.io/badge/Python-3.11-3776AB?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-150458?logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557C)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Plots-4C72B0)
![SciPy](https://img.shields.io/badge/SciPy-Hypothesis%20Testing-8CAAE6?logo=scipy&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

</div>

---

## 📌 Overview

This project analyzes farm-level agricultural data to understand how **seasonal variation** — in environmental conditions, resource usage, and farming practices — affects agricultural performance across India. It was completed as the Major Project for the **VOIS AICTE Virtual Internship, Batch 1 (2026–2027)**.

Rather than a generic pass over the dataset, the analysis is built around a focused problem: **do Kharif, Rabi, and Zaid seasons produce meaningfully different agricultural and economic outcomes — and if so, why?**

---

## 🎯 Problem Statement

Agricultural performance is shaped by seasonal shifts in rainfall, temperature, soil conditions, resource availability, and market conditions. Raw farm data alone doesn't reveal *how* performance changes across seasons or *what* patterns drive those differences. This project investigates seasonal differences in agricultural performance by uncovering meaningful patterns, trends, relationships, and anomalies within the dataset — and translates them into evidence-based recommendations.

---

## 🗂️ Dataset

| | |
|---|---|
| **File** | `seasonal_agriculture_performance_dataset.csv` |
| **Records** | 4,000 farms |
| **Features** | 28 |
| **Seasons** | Kharif, Rabi, Zaid |
| **Coverage** | 8 states · 10 districts · 8 crops · 4 irrigation methods |

<details>
<summary><strong>📋 Full column schema (click to expand)</strong></summary>

| Column | Description |
|---|---|
| `Farm_ID` | Unique identifier for each farm record |
| `State`, `District` | Geographic location of the farm |
| `Crop` | Crop grown (Rice, Wheat, Maize, Cotton, Pulses, Groundnut, Chilli, Sugarcane) |
| `Season` | Cropping season — Kharif, Rabi, or Zaid |
| `Farm_Area_Hectares` | Total cultivated area |
| `Rainfall_mm` | Rainfall received during the season |
| `Avg_Temperature_C` | Average temperature |
| `Humidity_pct` | Relative humidity |
| `Sunlight_Hours_Day` | Average daily sunlight hours |
| `Soil_pH`, `Soil_Moisture_pct` | Soil condition indicators |
| `Nitrogen_kg_ha`, `Phosphorus_kg_ha`, `Potassium_kg_ha` | Nutrient application rates (NPK) |
| `Irrigation_Method` | Drip, Flood, Rainfed, or Sprinkler |
| `Fertilizer_kg_ha`, `Pesticide_Litre_ha` | Input usage per hectare |
| `Seed_Quality_Score` | Seed quality rating (0–1) |
| `Yield_Tonnes_Ha` | Crop yield per hectare |
| `Production_Tonnes` | Total production volume |
| `Market_Price_INR_Tonne` | Market price per tonne |
| `Total_Cost_INR`, `Revenue_INR`, `Profit_INR` | Farm-level economics |
| `Water_Used_m3`, `Water_Efficiency_t_per_1000m3` | Water usage and efficiency |
| `Disease_Pest_Risk_pct` | Disease/pest risk score |

</details>

---

## 🔑 Key Questions Explored

- How does agricultural performance vary across seasons, and are the differences statistically real?
- Which environmental and resource-use characteristics change most between seasons?
- Do seasonal conditions actually correlate with yield outcomes — or are other factors driving performance?
- How do economic outcomes (cost, revenue, profit) differ by season?
- Are seasonal patterns consistent across different states and crops, or region/crop-specific?
- What unusual or counter-intuitive patterns exist in the data?

---

## 🧠 Methodology

1. **Data Cleaning** — season-wise median imputation for missing values, duplicate checks, and IQR-based outlier flagging (kept rather than dropped, since most "outliers" are legitimate — e.g. Sugarcane's naturally higher yield scale)
2. **Feature Engineering** — profit margin, cost-per-tonne, loss-making flag, and a **crop-normalized yield z-score** to enable fair cross-season comparison despite differing crop mixes
3. **Exploratory Data Analysis** — univariate distributions, seasonal boxplots/heatmaps across environmental, resource, and economic variables
4. **Correlation Analysis** — overall and within-season correlation between environmental factors and yield
5. **Statistical Testing** — Kruskal-Wallis tests (non-parametric, since yield/profit are heavily right-skewed), Bonferroni-corrected pairwise Mann-Whitney tests, and Chi-square tests of independence for categorical practices
6. **Pattern & Outlier Detection** — identifying unusual or counter-intuitive seasonal behavior
7. **Insight Synthesis** — data-driven conclusions and actionable recommendations

---

## 📈 Headline Findings

- **Season has a statistically significant effect on both yield and profit** (Kruskal-Wallis p < 0.001), confirmed pairwise across every season combination — even after normalizing yield within each crop.
- **Zaid is the weakest season economically** — the lowest yield, ~65% of its farms operate at a loss, and it's the only season with a *negative* total profit.
- **Kharif is "high risk, high reward"** — it delivers the highest total profit but also carries the highest disease/pest risk, driven by the same high rainfall and humidity that boost growth.
- **No single environmental factor strongly predicts yield** — rainfall, temperature, and soil moisture each correlate weakly with yield within a season, suggesting performance is driven by a combination of factors rather than one variable.
- **Irrigation and crop choices aren't adapted by season** — despite very different rainfall levels, irrigation method mix and crop mix are statistically independent of season (Chi-square, p > 0.05).

*(Full detail, charts, and statistical output are in the notebook.)*

---

## 📁 Project Structure

```
├── Seasonal_Agriculture_Performance_Analysis.ipynb   # Full analysis notebook
├── seasonal_agriculture_performance_dataset.csv      # Source dataset
└── README.md                                         # Project documentation
```

---

## 🚀 How to Run

1. Open `Seasonal_Agriculture_Performance_Analysis.ipynb` in **Google Colab**.
2. Run the setup cell to import libraries.
3. In the data-loading cell, either:
   - uncomment the `files.upload()` lines and select the CSV when prompted, **or**
   - upload `seasonal_agriculture_performance_dataset.csv` to the Colab file panel and keep the default path.
4. Run all remaining cells top to bottom — no other configuration needed.

---

## 🛠️ Tech Stack

`Python` · `Pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `SciPy` · `Jupyter / Google Colab`

---

## 👤 Author

**Sankalan**
Final-year B.Tech, Computer Science & Engineering

Submitted as part of the **VOIS AICTE Virtual Internship Program, Batch 1 (2026–2027)**.
