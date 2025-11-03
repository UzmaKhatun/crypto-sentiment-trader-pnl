# Sentiment and Trader Performance Analysis Results

## 1. Detailed Correlation Analysis
Correlation between Sentiment Metrics and PnL Metrics:
|                  |   total_closed_pnl |   avg_closed_pnl |   pnl_per_trade |   pnl_per_volume |
|:-----------------|-------------------:|-----------------:|----------------:|-----------------:|
| index_value      |             -0.083 |            0.037 |           0.037 |            0.064 |
| lag_index_value  |             -0.108 |            0.019 |           0.019 |            0.043 |
| sentiment_change |              0.068 |            0.050 |           0.050 |            0.058 |
| is_greed         |             -0.142 |            0.023 |           0.023 |            0.032 |

## 2. Grouped Analysis by Sentiment Classification
Mean and Median Trader Performance by Sentiment Classification:
| classification   |   ('total_closed_pnl', 'mean') |   ('total_closed_pnl', 'median') |   ('total_closed_pnl', 'count') |   ('avg_closed_pnl', 'mean') |   ('avg_closed_pnl', 'median') |   ('avg_closed_pnl', 'count') |   ('pnl_per_trade', 'mean') |   ('pnl_per_trade', 'median') |   ('pnl_per_trade', 'count') |   ('pnl_per_volume', 'mean') |   ('pnl_per_volume', 'median') |   ('pnl_per_volume', 'count') |   ('trade_count', 'mean') |   ('trade_count', 'median') |   ('trade_count', 'count') |
|:-----------------|-------------------------------:|---------------------------------:|--------------------------------:|-----------------------------:|-------------------------------:|------------------------------:|----------------------------:|------------------------------:|-----------------------------:|-----------------------------:|-------------------------------:|------------------------------:|--------------------------:|----------------------------:|---------------------------:|
| Extreme Fear     |                       52793.59 |                         22561.74 |                           14.00 |                        38.43 |                          11.57 |                         14.00 |                       38.43 |                         11.57 |                        14.00 |                         0.01 |                           0.00 |                         14.00 |                   1528.57 |                     1097.50 |                      14.00 |
| Fear             |                       36891.82 |                          1412.31 |                           91.00 |                        31.28 |                          18.22 |                         91.00 |                       31.28 |                         18.22 |                        91.00 |                         0.01 |                           0.00 |                         91.00 |                    679.53 |                       88.00 |                      91.00 |
| Neutral          |                       19297.32 |                          1818.57 |                           67.00 |                        63.82 |                          19.56 |                         67.00 |                       63.82 |                         19.56 |                        67.00 |                         0.01 |                           0.00 |                         67.00 |                    562.48 |                       50.00 |                      67.00 |
| Greed            |                       11198.59 |                           717.57 |                          192.00 |                        39.62 |                          11.81 |                        192.00 |                       39.62 |                         11.81 |                       192.00 |                         0.01 |                           0.00 |                        192.00 |                    261.98 |                       48.00 |                     192.00 |
| Extreme Greed    |                       23817.29 |                          3127.54 |                          114.00 |                        56.74 |                          27.24 |                        114.00 |                       56.74 |                         27.24 |                       114.00 |                         0.02 |                           0.01 |                        114.00 |                    350.81 |                      133.00 |                     114.00 |

## 3. Statistical Significance (ANOVA)
ANOVA F-statistic for Total PnL across Sentiment Classes: 2.769
ANOVA P-value for Total PnL across Sentiment Classes: 0.027
Conclusion: The mean daily total PnL is significantly different across the sentiment classifications.

## 4. Regression Analysis: Sentiment Index vs. Total PnL
                            OLS Regression Results                            
==============================================================================
Dep. Variable:       total_closed_pnl   R-squared:                       0.007
Model:                            OLS   Adj. R-squared:                  0.005
Method:                 Least Squares   F-statistic:                     3.266
Date:                Mon, 03 Nov 2025   Prob (F-statistic):             0.0714
Time:                        17:46:35   Log-Likelihood:                -6022.3
No. Observations:                 478   AIC:                         1.205e+04
Df Residuals:                     476   BIC:                         1.206e+04
Df Model:                           1                                         
Covariance Type:            nonrobust                                         
===============================================================================
                  coef    std err          t      P>|t|      [0.025      0.975]
-------------------------------------------------------------------------------
const        4.053e+04   1.11e+04      3.666      0.000    1.88e+04    6.23e+04
index_value  -317.7337    175.808     -1.807      0.071    -663.190      27.723
==============================================================================
Omnibus:                      428.433   Durbin-Watson:                   1.378
Prob(Omnibus):                  0.000   Jarque-Bera (JB):            15675.425
Skew:                           3.727   Prob(JB):                         0.00
Kurtosis:                      30.046   Cond. No.                         212.
==============================================================================

Notes:
[1] Standard Errors assume that the covariance matrix of the errors is correctly specified.

## 5. Regression Analysis: Lagged Sentiment Index vs. Total PnL
                            OLS Regression Results                            
==============================================================================
Dep. Variable:       total_closed_pnl   R-squared:                       0.012
Model:                            OLS   Adj. R-squared:                  0.010
Method:                 Least Squares   F-statistic:                     5.594
Date:                Mon, 03 Nov 2025   Prob (F-statistic):             0.0184
Time:                        17:46:35   Log-Likelihood:                -6021.1
No. Observations:                 478   AIC:                         1.205e+04
Df Residuals:                     476   BIC:                         1.205e+04
Df Model:                           1                                         
Covariance Type:            nonrobust                                         
===================================================================================
                      coef    std err          t      P>|t|      [0.025      0.975]
-----------------------------------------------------------------------------------
const            4.637e+04    1.1e+04      4.203      0.000    2.47e+04    6.81e+04
lag_index_value  -414.8722    175.405     -2.365      0.018    -759.535     -70.209
==============================================================================
Omnibus:                      421.662   Durbin-Watson:                   1.367
Prob(Omnibus):                  0.000   Jarque-Bera (JB):            15380.918
Skew:                           3.632   Prob(JB):                         0.00
Kurtosis:                      29.824   Cond. No.                         212.
==============================================================================

Notes:
[1] Standard Errors assume that the covariance matrix of the errors is correctly specified.

