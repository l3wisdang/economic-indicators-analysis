# 🌍 Global Economic Indicators Analysis

This project explores how key macroeconomic indicators such as inflation, interest rates, GDP per capita, unemployment and income inequality relate to one another across countries, and what those relationships mean for financial market stakeholders. Using World Bank data covering 2000 to 2023, I deliberately chose a window that captures the Dot-Com Bubble, the 2008 Financial Crisis, the Eurozone Debt Crisis and COVID-19, so I could see how economies respond to shocks and how those responses show up in the data.

What makes the project distinctive is its global, comparative perspective: rather than studying a single country, it looks across nations to spot patterns and highlight indicators that might signal economic risk or recovery.

The full written report is included in this repository: [Economic_Indicators_Report.pdf](Economic_Indicators_Report.pdf)

## 📦 Technologies

- `Python`
- `pandas`
- `Matplotlib` and `Seaborn`
- `Plotly`
- `Jupyter Notebook`

## ⚙️ What I Built

**Data collection**

I initially explored Kaggle and Reddit for datasets, but most lacked the required time range, had too few rows, or used inconsistent timeframes that would have made cross-country comparison unreliable. I settled on World Bank Open Data, which offered consistent formatting, full 2000 to 2023 coverage, and a wide enough range of indicators to compare countries on structural strengths and weaknesses rather than just headline growth.

**Data cleansing**

I renamed coded column headers into readable names, converted placeholder values into proper NaNs, and experimented with imputation strategies. Means proved sensitive to extreme values, so I replaced missing values using the median instead, after first filling with zeros so the median calculation would not skip NaNs entirely and skew results.

**Reshaping for analysis**

The raw data stacked every indicator in a single column, which made comparison and graphing complicated. I melted the year columns into rows and then pivoted the dataset from long to wide format, so each row became a unique country-year combination and each indicator its own column. This structure enabled both cross-sectional (country to country) and longitudinal (year over year) analysis.

**Visualisation**

I produced a Pearson correlation heatmap across all indicators, a pre- versus post-COVID GDP per capita comparison for the top 20 countries, and an interactive Plotly radar chart comparing China and the United States across GDP per capita, inflation, unemployment and FDI net inflows.

## 📚 What I Learned

**Global indicators are only weakly linked**

The heatmap showed that most indicators have weak linear relationships globally: income inequality and unemployment were moderately positively correlated (+0.26), interest and inflation rates slightly negatively correlated (-0.21), consistent with central banks raising rates to fight inflation, while GDP per capita barely correlated with anything. Wealth alone does not predict inequality or labour market conditions, which reinforced for me why country-level analysis matters.

**The COVID recovery was uneven**

China recorded the largest pre- to post-COVID GDP per capita rise, driven by its early industrial rebound and export momentum, with the US close behind on fiscal stimulus and tech growth. Developed economies like Germany, Japan and the UK gained far less. From a markets lens, strong GDP rebounds boost investor confidence and attract foreign investment, so this shifting landscape matters for asset allocation.

**Data work is most of the work**

The majority of the project was acquiring, cleaning and restructuring data rather than analysing it. Choosing median over mean imputation, and understanding why pivoting the data mattered for every downstream step, taught me more about practical analytics than the charts themselves.

## 💬 How can it be improved?

- Add statistical testing rather than relying on visual correlation alone
- Extend the analysis with country-level regressions or clustering by economic profile
- Automate data retrieval through the World Bank API instead of a static CSV
- Note that the interactive Plotly chart does not render in GitHub's notebook preview, so a static image export could be added

## 🔌 Running the Project

1. Clone the repository to your local machine
2. Install dependencies: `pip install pandas matplotlib seaborn plotly`
3. Open the notebook in Jupyter:

```bash
jupyter notebook economic_indicators_analysis.ipynb
```

The notebook reads `Economic_Indicators.csv`, which is included in the repository.

## 🙏 Acknowledgments

Data sourced from [World Bank Open Data](https://data.worldbank.org/). The data cleaning and visualisation approach drew on several references, including W3Schools (heatmaps), Stack Overflow (pivoting), Plotly documentation (radar charts), and analysis notebooks by Zabihullah18 and A. Mulla. Full references are listed in the [report](Economic_Indicators_Report.pdf).
