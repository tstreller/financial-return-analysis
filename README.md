# Financial Return Analysis

A compact quantitative-finance project exploring daily return and volatility characteristics of S&P 500 and Gold futures with Python.

The goal is **not** to build or claim a profitable trading strategy. The project demonstrates a transparent workflow: obtain data, transform prices into returns, summarize distributions, visualize volatility, run simple statistical tests, and state limitations clearly.

## Questions

- What do daily return distributions for ES and GC look like?
- How volatile are the two markets over time?
- How strongly are their daily returns correlated?
- Is the estimated mean daily return statistically distinguishable from zero in the selected sample?

## Markets

- **ES=F** — E-mini S&P 500 futures
- **GC=F** — Gold futures

Data is downloaded with `yfinance` for an educational portfolio exercise. It is **not treated as research-grade futures data**.

## Sample Results

The executed notebook currently covers **1,421 paired daily-return observations** from January 2021 through August 2026.

| Metric | ES | GC |
|---|---:|---:|
| Mean daily return | 0.0572% | 0.0644% |
| Daily volatility | 1.0487% | 1.1623% |
| Annualized volatility | 16.65% | 18.45% |
| Skewness | 0.143 | -0.926 |
| Excess kurtosis | 6.621 | 8.627 |
| 95% CI for mean daily return | 0.0026% to 0.1118% | 0.0039% to 0.1249% |
| One-sample t-test p-value | 0.03995 | 0.03695 |

The sample daily-return correlation between ES and GC is **0.1039**.

These results are descriptive and exploratory. A p-value below 0.05 in this convenience sample does **not** establish a persistent return premium or tradable edge. Vendor construction, futures-roll effects, regime dependence, multiple testing, implementation costs, and true out-of-sample validation remain unresolved.

## Methods

1. Data acquisition and validation
2. Simple daily returns
3. Descriptive statistics
4. Return distributions
5. 20-day rolling annualized volatility
6. Correlation
7. 95% confidence intervals
8. One-sample t-tests against a zero mean
9. Interpretation and limitations

## Repository Structure

```text
financial-return-analysis/
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   └── README.md
└── notebooks/
    └── return_analysis.ipynb
```

## Run Locally

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

Then open `notebooks/return_analysis.ipynb`.

## Research Discipline

A statistically interesting result is not automatically economically meaningful, robust, or tradable.

Limitations include vendor data quality, futures-roll construction, regime dependence, multiple testing, implementation costs, and the absence of true out-of-sample validation in this introductory project.

## Author

Tino Streller  
Business Administration student, University of Greifswald  
Quantitative Finance · Systematic Research · Financial Markets
