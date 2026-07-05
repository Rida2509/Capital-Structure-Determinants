# Project-
Capital Structure Determinants: Trade-off Theory vs Pecking Order Theory
Overview
This project investigates the determinants of corporate capital structure using firm-level financial data derived from SEC filings of publicly listed United States companies. The analysis tests two competing theoretical frameworks in corporate finance, Trade-off Theory and Pecking Order Theory, by examining the relationship between firm profitability and financial leverage.
Trade-off Theory predicts a positive relationship between profitability and leverage, based on the idea that firms balance the tax benefits of debt against the costs of financial distress. Pecking Order Theory predicts a negative relationship, based on the idea that firms prefer internal financing over external debt and equity. This project uses empirical data to determine which theory better explains observed leverage patterns.
Dataset
•Name: Financial Statement Data Sets (Company Facts)
•Source: Kaggle, derived from SEC EDGAR company facts filings
•Link: https://www.kaggle.com/datasets/vadimvanak/company-facts-2
•Coverage: US-GAAP financial statement data extracted from SEC filings of listed United States companies, covering periods from January 2009 onward
•Raw size: 79,448,144 individual financial statement line items across 9,641 unique XBRL tags
Project Workflow
•Set up the environment and download the dataset from Kaggle
•Inspect the raw dataset structure and identify relevant financial tags
•Filter the dataset to the six financial tags required for the analysis
•Merge financial data with filing metadata and restrict to annual (Form 10-K) filings
•Deduplicate financial values by company and fiscal period
•Correct for quarterly values embedded within annual filings
•Recover missing Liabilities values using the accounting identity
•Construct core capital structure variables
•Clean implausible values and apply winsorization to limit the effect of outliers
•Conduct descriptive statistics and exploratory data analysis
•Perform correlation analysis
•Estimate ordinary least squares regression models
•Conduct sector-level analysis of leverage
•Summarize findings and draw conclusions
Variables Constructed
Variable	Definition
Leverage	Total Liabilities divided by Total Assets
Profitability	Net Income divided by Total Assets
Tangibility	Net Property, Plant and Equipment divided by Total Assets
Size	Natural logarithm of Total Assets
Revenue Growth	Percentage change in Revenues relative to the prior fiscal year

Methodology
The analysis is based on a company-year panel constructed from raw XBRL financial statement data. After filtering, deduplication, and cleaning, the final analytical sample consists of 9,733 firm-year observations across approximately 6,600 unique companies. Two ordinary least squares regression models are estimated, with Leverage as the dependent variable.
•Model 1: Leverage regressed on Profitability, Tangibility, and Size, using the larger available sample
•Model 2: Leverage regressed on Profitability, Tangibility, Size, and Revenue Growth, using a smaller subsample where Revenue Growth data is available
Key Findings
•Profitability shows a negative and statistically significant relationship with Leverage in both regression models, with coefficients of -0.2305 and -0.3425 respectively. This finding is consistent with Pecking Order Theory rather than Trade-off Theory.
•Tangibility shows a positive and statistically significant relationship with Leverage in the larger sample, consistent with the role of tangible assets as collateral.
•Size shows a small positive and statistically significant relationship with Leverage in the larger sample.
•Revenue Growth does not show a statistically significant relationship with Leverage.
•Average leverage varies meaningfully across industry sectors, with Retail Trade, Agriculture, and Wholesale Trade exhibiting the highest average leverage, and Manufacturing and Finance, Insurance, and Real Estate exhibiting comparatively lower average leverage.
Repository Structure
.
├── Untitled1.ipynb                  Main analysis notebook
├── Capital_Structure_Report.docx    Full written report of the analysis
└── README.docx                      Project documentation

Tools and Libraries
•Python
•pandas
•pyarrow
•numpy
•matplotlib
•seaborn
•statsmodels
How to Run
1. Clone this repository.
2. Install the required Python packages: pandas, pyarrow, numpy, matplotlib, seaborn, and statsmodels.
3. Obtain a Kaggle API credential file (kaggle.json) from a Kaggle account and place it in the expected directory as described in the notebook.
4. Run the notebook cells in sequence to download the dataset, construct the panel, and reproduce the analysis.
Conclusion
The empirical results of this project indicate that the financing behavior of the sampled United States public companies is more consistent with Pecking Order Theory than with Trade-off Theory. More profitable firms in the sample tend to carry lower leverage, suggesting a preference for internal financing over external debt. Firm-level characteristics such as tangibility and size, along with industry classification, also play a meaningful role in shaping capital structure outcomes.
Author
Rida Mustafa
