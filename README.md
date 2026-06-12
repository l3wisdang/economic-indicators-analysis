# 🌍 Global Economic Indicators Analysis

This project explores how key macroeconomic indicators such as inflation, interest rates, GDP per capita, unemployment and income inequality relate to one another across countries, and what those relationships mean for financial market stakeholders. Using World Bank data covering 2000 to 2023, a window chosen to capture the Dot-Com Bubble, the 2008 Financial Crisis, the Eurozone Debt Crisis and COVID-19, I cleaned and restructured the raw data in pandas, then analysed it through a correlation heatmap, a pre- versus post-COVID GDP comparison, and an interactive radar chart comparing China and the US.

📄 **Full analysis, figures and references:** [Economic_Indicators_Report.pdf](Economic_Indicators_Report.pdf)

## 📦 Technologies

- `Python` and `pandas`
- `Matplotlib`, `Seaborn`, `Plotly`
- `Jupyter Notebook`

## 📚 What I Learned

**Global indicators are only weakly linked.** Most indicators showed weak linear relationships globally: inequality and unemployment were moderately correlated (+0.26), interest and inflation slightly negatively (-0.21), while GDP per capita barely correlated with anything. Wealth alone does not predict inequality or labour conditions, which is exactly why country-level analysis matters.

**The COVID recovery was uneven.** China and the US recorded the largest GDP per capita gains while developed economies like Germany and Japan lagged, a shifting landscape that matters for investor confidence and asset allocation.

**Data work is most of the work.** The majority of the project was sourcing, cleaning and reshaping data: choosing median over mean imputation, and pivoting from long to wide format so each country-year became a row. Those decisions shaped every downstream result more than the charts did.

## 💬 How can it be improved?

- Add statistical testing rather than relying on visual correlation alone
- Automate data retrieval through the World Bank API instead of a static CSV
- Export the interactive Plotly chart as a static image, since it does not render in GitHub's notebook preview

## 🔌 Running the Project

1. Clone the repository and install dependencies: `pip install pandas matplotlib seaborn plotly`
2. Open the notebook:

```bash
jupyter notebook economic_indicators_analysis.ipynb
```

The notebook reads `Economic_Indicators.csv`, which is included in the repository.

## 🙏 Acknowledgments

Data sourced from [World Bank Open Data](https://data.worldbank.org/). The cleaning and visualisation approach drew on W3Schools, Stack Overflow, Plotly documentation, and analysis notebooks by Zabihullah18 and A. Mulla; full references are in the [report](Economic_Indicators_Report.pdf).
