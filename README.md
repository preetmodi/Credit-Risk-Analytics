# Credit-Risk-Analytics

## Problem Statement
Lending Club (https://www.lendingclub.com) is a well-known peer-to-peer (P2P) lenders operating in North America. Its business model is to let potential investors diversify their risk by splitting their investments across multiple loans. To add transparency to their models, Lending Club has been realising their lending history in its entirety, available for the period 2007 to 2018 for the United States, along with loan performance for them. The dataset you are given has all loans that are either current or defaulted has approximately 1.3 million loans and around 128 variables. Not all these variables are predictive. You are provided a data dictionary available in the Excel file “LCDataDictionaryClean.xlsx”. The first sheet has the variables that were available at origination time, right after the loan was approved, and the performance tab shows the variables that are available currently (as the loan is repaid).

In this coursework, you will develop a fully compliant advanced IRB model for origination scoring from the data they make available, from the raw data to the level 2 calibration, using what you have learned in the lectures. The objective of the coursework is to estimate the capital requirements for Lending Club were they to be regulated (they are currently not).

Final Report - [Report (PDF)](https://github.com/preetmodi/Credit-Risk-Analytics/blob/main/Report.pdf)

1. (15%) Clean the dataset so it is ready to apply models to it. Discuss all your decisions. Design three variables from the dataset that you think could improve prediction (using e.g. ratios, averages, trends, aggregations, etc. Please note normal cleaning does not count). Explain your rationale on choosing those variables.

> Files:
>- [Data_Cleaning_P](https://github.com/preetmodi/Credit-Risk-Analytics/blob/main/Data_Cleaning_P.ipynb)
>- [Data_Cleaning_V](https://github.com/preetmodi/Credit-Risk-Analytics/blob/main/Data_Cleaning_V.ipynb)
>- [Data_Cleaning_H](https://github.com/preetmodi/Credit-Risk-Analytics/blob/main/Data_Cleaning_H.ipynb)

2. (10%) Calculate the WoE and perform the variable selection procedures you see fit. Explain your decisions.

> Files:
>- [All_WoE](https://github.com/preetmodi/Credit-Risk-Analytics/blob/main/All_WOE.ipynb)
>- [Woe_calculation_H](https://github.com/preetmodi/Credit-Risk-Analytics/blob/main/Woe_calculation_H.ipynb)
>- [WoE_V](https://github.com/preetmodi/Credit-Risk-Analytics/blob/main/WoE_V.ipynb)
>- [Woe_calculation_P](https://github.com/preetmodi/Credit-Risk-Analytics/blob/main/Woe_calculation_P.ipynb)

3. (15%) Construct a scorecard which can model the probability of default for the loans. As you do not have information regarding 12-month performance, use the status “Chargeoff” or “Default” as the objective variable from variable “loan_status”. How many variables do you recommend using?

> Files:
> - [Scorecard and Logistic Regression](https://github.com/preetmodi/Credit-Risk-Analytics/blob/main/Scorecard_logistic_reg.ipynb)

4. (20%) Compare your scoring model with an XGBoosting model trained over the data without the WoE transformation. Use cross-validation to determine your optimal parameters, if necessary, and discuss the accuracy metrics you deem relevant. Compare the performance of the these two and discuss your findings.

> Files:
> - [XGB](https://github.com/preetmodi/Credit-Risk-Analytics/blob/main/XGB.ipynb)

5. (10%) Discuss the variable importance for both models, using SHAP values for the XGB model. Do the logistic regression and XGB agree? Why?

> Files:
> - [Shapley Values PDF](https://github.com/preetmodi/Credit-Risk-Analytics/blob/main/ShapSummaryPlot.pdf)

6. (10%) Using the information from Performance variables, calculate an expected recovery rate (LGD) and loan profit, and design an optimal cutoff point. Consider the cost of capital is 50% of the charged interest rate to calculate the cutoff.

> Files:
> - [Performance Variable Analysis](https://github.com/preetmodi/Credit-Risk-Analytics/blob/main/performance_variable_analysis.ipynb)
> - [LGD_Caliberation](https://github.com/preetmodi/Credit-Risk-Analytics/blob/main/LGD_Caliberation.ipynb)

7. (10%) Using the monthly macroeconomic information you consider relevant (see for example https://stats.oecd.org/Index.aspx), calibrate a long-run PD for the loans granted regressing your monthly Lending Club’s PDs (from your objective variable and the issue date) per rating (from the variable ‘grade’) against the macroeconomic variables1.

> Files:
> - [PD Calibration](https://github.com/preetmodi/Credit-Risk-Analytics/blob/main/PD%20calibration.ipynb)
