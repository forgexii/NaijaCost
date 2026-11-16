# NaijaCost: Nigerian Food Price Inflation & Market Volatility Analysis

An end-to-end econometric and data science investigation into food price inflation, market volatility, regional supply chain friction, and macroeconomic shocks across Nigeria (2002–2026).

---

## 📌 Executive Summary
**NaijaCost** investigates the empirical dynamics of food affordability and staple commodity pricing across Nigeria's 36 states and Federal Capital Territory. Analyzing **91,216 transaction records** spanning 118 markets and 43 commodities collected by the **UN World Food Programme (WFP)** and Humanitarian Data Exchange (HDX), this project evaluates:

1. **Macroeconomic Policy Shocks**: Quantifying the impact of the May 2023 petrol subsidy removal and the unification/float of the Naira foreign exchange window on staple food costs.
2. **Fuel Price Spillover Elasticity**: Measuring the econometric pass-through of commercial fuel prices (petrol/gasoline) into grain and tuber retail prices.
3. **Regional Market Fragmentation**: Testing spatial price parity between Northern agricultural production zones and Southern coastal consumption centers.
4. **Intermediary Markups**: Evaluating retail consumer premiums over bulk wholesale market prices.

---

## 🗂️ Project Structure

```
NaijaCost/
│
├── data/
│   ├── raw/
│   │   ├── wfp_food_prices_nga.csv          # Granular market price data (91,216 rows, 2002–2026)
│   │   ├── wfp_markets_nga.csv              # Market locations and geographic coordinates
│   │   └── NGA_RTP_details_mkt_2007_...     # Original World Bank RTP metadata summary
│   └── processed/
│       ├── naijacost_cleaned_food_prices.csv # Normalized units (KG, L, Tubers) and zones (16.5 MB)
│       └── naijacost_monthly_summary.csv     # Zonal and monthly aggregated indicators
│
├── notebooks/
│   ├── 01_Data_Collection_and_Exploration.ipynb # Data collection, API scraping, and schema audit
│   ├── 02_Data_Cleaning.ipynb                   # Unit normalization, zone mapping, QA filtering
│   ├── 03_Exploratory_Data_Analysis.ipynb       # Price paths, macro shocks, and spread analysis
│   ├── 04_Statistical_Analysis.ipynb            # Welch t-test, ANOVA, OLS fuel elasticity, ADF test
│   ├── 05_Data_Visualization.ipynb             # High-resolution publication visualizations
│   └── 06_Insights_and_Reporting.ipynb          # Policy recommendations, executive synthesis
│
├── reports/
│   ├── naijacost_executive_summary_metrics.csv  # Pre vs post-2023 summary price metrics
│   └── figures/
│       ├── fig1_staple_price_trends.png         # Multi-staple historical trend (2010–2026)
│       ├── fig2_macro_shocks_subsidy_impact.png # Pre vs Post May 2023 price surge
│       ├── fig3_zone_price_disparities.png      # Regional local rice price boxplots
│       ├── fig4_commodity_fuel_correlation_heatmap.png # Cross-commodity & petrol correlation
│       ├── fig5_retail_vs_wholesale_spread.png  # Retail markup percentage (2018–2026)
│       └── fig6_seasonality_patterns.png        # Intra-year monthly seasonality index
│
├── requirements.txt                             # Python dependencies
└── README.md                                    # Project documentation
```

---

## 🔬 Key Empirical Findings

1. **Substantial Post-Subsidy Acceleration (May 2023)**:
   - Average retail prices for staple carbohydrates escalated by **150% to over 300%** between 2023 and 2026.
   - Local rice increased from an average baseline of ~NGN 450/KG to peak above NGN 1,300/KG.
   - White Garri, historically Nigeria's most resilient safety-net carbohydrate, experienced unprecedented price acceleration exceeding NGN 850/KG.

2. **High Fuel Price Transmission ($R^2 = 0.869$)**:
   - Ordinary Least Squares (OLS) regression demonstrates that **86.9%** of the monthly variance in local rice prices is explained by commercial fuel price movements ($p < 0.0001$).
   - For every **100 NGN increase in petrol prices**, retail staple food prices increase by approximately **52.4 NGN/KG** due to long-haul freight and milling expenses.

3. **Rejection of Spatial Market Integration**:
   - Welch's two-sample t-test ($t = 16.48, p = 1.78 \times 10^{-52}$) and ANOVA tests ($F = 88.42, p < 10^{-53}$) strongly reject regional price parity.
   - Substantial transport overheads, interstate informal road tolls, and supply chain friction prevent price equalization across Nigerian geopolitical zones.

4. **Retail Margin Strain**:
   - Retail consumers incur an average **15% to 35% markup** over bulk wholesale prices, heavily penalizing low-income households unable to buy in bulk sacks.

---

## 🚀 Setup & Execution

### 1. Environment Setup
```bash
# Activate virtual environment
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### 2. Running Notebooks
Launch your Jupyter environment:
```bash
jupyter lab
# or
jupyter notebook
```
Execute the notebooks in sequence from `01_Data_Collection_and_Exploration.ipynb` through `06_Insights_and_Reporting.ipynb`.

---

## 📊 Data Source Attribution
- **Source**: United Nations World Food Programme (WFP) / Humanitarian Data Exchange (HDX).
- **Dataset**: [WFP Food Prices for Nigeria](https://data.humdata.org/dataset/wfp-food-prices-for-nigeria).
- **License**: Creative Commons Attribution 4.0 International (CC BY 4.0).
