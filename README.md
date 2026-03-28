# ECON-UB-232-Data-Bootcamp-Midterm Project 
---

## 📌 Project Overview

This project aims to give an idea of applying **Exploratory Data Analysis Skills from the Data Bootcamp Course** in a real business scenario. We will develop a basic understanding of the **international trade landscape** and understand **how certain economic factors (e.g. exchange rates, energy prices, etc.) influence U.S. international trade**, particularly exports to other nations.

## 🗂️ Repository Structure

```
├── Data_Bootcamp_Midterm_Project_V2.ipynb   # Main Jupyter Notebook (full Midterm Project code)
├── Data Bootcamp Midterm Project Write-up.pdf             # Midterm Project Write Up
├── README.md
├── requirements.txt                         
```

---

## 📁 APIs

This project uses datasets from **2 APIs**:

| API | Description |
|---|---|
| `U.S. Census Bureau` | U.S. International Trade information |
| `FRED` | Economic Data Series (e.g. Exchange Rates, Energy Prices, etc.) |

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/DSin145/DATA_BOOTCAMP_MIDTERM_PROJECT.git
cd DATA_BOOTCAMP_MIDTERM_PROJECT
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the notebook

```bash
jupyter notebook Data_Bootcamp_Midterm_Project_V2.ipynb
```

Or open it directly in **Google Colab** by uploading to your Drive and mounting it.

---

## 📈 Executive Summary

**Data Bootcamp Midterm Project** | Prepared using U.S. Census Bureau API & FRED Data (2010–2025)

---

### Overview

This project applies exploratory data analysis (EDA) techniques to investigate U.S. international trade patterns and the macroeconomic factors that influence them. Using two live data sources — the U.S. Census Bureau API (trade flows by industry and country, 2016–2025) and the Federal Reserve Economic Data (FRED) API (exchange rates, oil prices, and interest rates, 2010–2025) — the analysis addresses two core questions (and many sub-questions within each section):

- What does the U.S. trade, and with whom?
- What economic variables drive U.S. export performance?

---

## Datasets & Technical Approach

The project is built entirely in Python (Colab Notebook), using `requests` to pull live API data, `pandas` for data wrangling, and `matplotlib`/`seaborn` for visualization.

**Key data pipelines include:**

- **Census Bureau NAICS & End-Use APIs** — Looped across 2016–2025 to collect annual export and import values by industry classification and by country/regional bloc, then concatenated into master DataFrames and cleaned of null or placeholder values.
- **FRED API** — Fetched time series for USD/JPY, USD/EUR, and USD/CNY exchange rates; WTI crude oil prices; and the Federal Funds Rate, resampled to monthly frequency and merged with export data for correlation analysis.

---

## Key Findings

### 1. Trade Structure: Exports
U.S. exports are overwhelmingly concentrated in manufactured goods, with transportation equipment, chemicals, and computer products also ranking highly. Export volumes took a sharp hit in 2020 due to COVID-19 but recovered rapidly. Manufactured goods reached record highs by 2025, reflecting durable global demand for U.S. industrial and technical output.

### 2. Trade Structure: Export Destinations
The U.S. exports primarily to economically integrated blocs (OECD, APEC, NATO, and USMCA). The post-2020 recovery showed a "V-shaped" turn concentrated in these same established partners rather than a diversification into new markets, suggesting U.S. trade growth is deepening existing relationships rather than expanding geographically.

### 3. Trade Structure: Imports
Imports mirror the export concentration in manufactured goods, with post-2020 values surpassing $2.5 trillion annually. Oil & gas and pharmaceuticals saw the most dramatic percentage increases after 2020 — likely reflecting pandemic-driven supply chain restructuring and global energy volatility in 2022–2023. Import sources remained heavily concentrated in APEC and OECD nations.

### 4. Economic Factor — Exchange Rates *(Weak Relationship)*
The analysis examined USD/JPY and USD/EUR exchange rates against U.S. exports to Japan and France. Despite the hypothesis that a stronger dollar would reduce exports, no consistent pattern was observed. The conclusion is that exchange rates are not a reliable standalone predictor of U.S. export volume.

### 5. Economic Factor — Oil Prices *(Moderate Relationship)*
The correlation between U.S. exports and WTI crude oil prices was calculated at **r = 0.307**, indicating a weak-to-moderate positive relationship. This likely reflects oil prices functioning as a proxy for global economic activity — when the world economy is strong, both oil demand and U.S. exports rise together.

### 6. Economic Factor — Interest Rates *(Strongest Relationship)*
The Federal Funds Rate showed the strongest correlation with U.S. exports at **r = 0.711**. While counterintuitive, this likely reflects the fact that the Fed raises rates during economic expansions, which are also the periods when trade activity is highest. Interest rates here serve as a signal of macroeconomic strength, not a direct cause of export growth.

---

## Conclusions

U.S. international trade is structurally dominated by manufactured goods and anchored in a stable, narrow set of high-income partner nations. The COVID-19 disruption of 2020 was significant but short-lived, with a swift V-shaped recovery. Among the macroeconomic factors examined:

| Factor | Correlation (r) | Relationship |
|---|---|---|
| Federal Funds Rate | 0.711 | Strong (proxy for economic cycles) |
| WTI Oil Prices | 0.307 | Weak-to-moderate |
| Exchange Rates | — | Weak / inconsistent |

These findings suggest that U.S. export performance is primarily shaped by global macroeconomic conditions and long-term structural demand, rather than any single currency or price variable.
