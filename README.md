# 🧠 Crypto Sentiment & Trader Performance Analysis

### Project Title: The Contrarian Edge: Analyzing Hyperliquid Trader Performance Against Bitcoin Sentiment

---

## 👋 Welcome to the Project!

This repository contains the full analysis for a data science assignment focused on uncovering the relationship between Bitcoin market sentiment and the real-world trading performance of users on the Hyperliquid platform.

The core idea? To test the famous contrarian trading adage: "Be fearful when others are greedy."

The results are fascinating and provide a strong, data-backed foundation for developing smarter, sentiment-aware trading strategies.

---

## 🎯 The Goal

The primary objective was to merge two distinct datasets—the daily Bitcoin Fear & Greed Index (FGI) and granular historical trade data—to determine if market emotion acts as a reliable indicator for collective trader profitability.

Key Insight: We found a statistically significant inverse relationship, suggesting that when the market is at its most "Greedy," the aggregate trader base tends to perform poorly the following day.

---

## 📊 Data Sources

The analysis is built upon two rich datasets:

1.Bitcoin Fear & Greed Index (FGI): Provides a daily snapshot of market emotion, ranging from Extreme Fear (0) to Extreme Greed (100).

2.Hyperliquid Historical Trade Data: Contains millions of individual trade records, including execution price, size, side (Buy/Sell), and the crucial closed_pnl (profit and loss) for each transaction.

---

## 🛠️ Project Structure & Code Explained

The analysis pipeline is broken down into modular Python scripts, making the process clear and repeatable.

|----------------|
|File Name|What it Does (In Simple Terms)|
|data_prep.py|The Initial Clean-Up. Loads the raw CSV files, identifies the correct column headers, and fixes messy data formats (like converting text dates into proper date objects).|
|data_processing.py|The Data Aggregator. Takes the cleaned trade data and groups it by day. It calculates the Total Daily PnL and other performance metrics, then merges this summary with the daily Fear & Greed Index.|
|eda_and_feature_engineering.py|The Insight Builder. Explores the merged data (EDA) to understand distributions and trends. Crucially, it creates new features like the previous day's sentiment (lag_index_value) to test for delayed effects.|
|sentiment_performance_analysis.py|The Statistical Core. Runs the heavy-duty math, including ANOVA (to check if PnL is different across sentiment groups) and Regression (to see if sentiment is a reliable predictor of PnL). This script confirms the contrarian signal.|
|visualizations.py|The Storyteller. Generates all the charts and graphs used in the final report, visually demonstrating the relationship between market sentiment and trader profitability over time.|
|analysis_report.pdf|The Final Report. A comprehensive write-up of the entire project, including methodology, findings, and actionable trading strategy recommendations.|


📈 Key Findings

The analysis strongly supports a contrarian approach to trading based on the Fear & Greed Index:

•
Highest Profits During Fear: The days where the aggregate trader base saw the highest mean profits occurred during periods classified as Extreme Fear.

•
Greed Hurts Tomorrow's PnL: The most statistically significant finding was that a high level of Greed on one day is associated with a lower total PnL for traders on the following day. This suggests a collective behavioral mistake when the market gets too excited.

💡 Strategy Recommendation

The data suggests using the FGI as a behavioral filter for trading decisions:

Sentiment State
FGI Range
Recommended Action
Extreme Greed
FGI > 75
Risk-Off / Short Bias. Be cautious, take profits, or look for short opportunities, especially the day after this reading.
Extreme Fear
FGI < 25
Risk-On / Long Bias. Look for opportunities to enter long positions, as these periods historically precede the most profitable days.





This project was completed as part of a data science assignment. All code and analysis are original.

