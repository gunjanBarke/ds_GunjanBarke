# 📊 Trader Sentiment Analysis

📌 Overview
This project explores the relationship between trader behavior and market sentiment using two datasets:

Bitcoin Market Sentiment Dataset – Market mood labeled as Fear or Greed

Historical Trader Data from Hyperliquid – Includes trading activity, profitability, volume, and leverage

The goal is to identify hidden patterns that show how traders react to different sentiment phases and whether their actions align or diverge from market mood.

📂 Datasets
1. Bitcoin Market Sentiment
Column	Description
Date	Date of the sentiment reading
Classification	Market sentiment – Fear or Greed

2. Trader Data (Hyperliquid)
Column	Description
account	Trader account ID
symbol	Trading pair (e.g., BTC-USDT)
execution price	Price at which trade was executed
size	Trade size (volume)
side	Buy/Sell
time	Timestamp of trade
start position	Position size before trade
event	Type of trade event
closedPnL	Profit/Loss from trade
leverage	Leverage used

🎯 Objectives
Analyze trader profitability, risk exposure, and trading volume under Fear vs Greed conditions

Compute rolling correlation between sentiment score and trader PnL

Identify possible predictive signals for better trading strategies

🛠️ Methodology
Data Cleaning & Preprocessing

Merge trader data with sentiment classification

Convert Classification to numeric sentiment score (Fear = -1, Greed = 1)

Parse date columns

Feature Engineering

Calculate average daily PnL, volume, leverage

Aggregate by date

Analysis

Group by sentiment phase and compare metrics

Calculate 30-day rolling correlation between sentiment score and PnL

Visualize key trends

Visualization

Time-series plots

Rolling correlation graphs

Summary tables

📈 Example Rolling Correlation Output

📜 How to Run
bash
Copy
Edit
# 1. Install dependencies
pip install pandas matplotlib

# 2. Place datasets in the `data/` folder
#    - bitcoin_sentiment.csv
#    - trader_data.csv

# 3. Run the analysis
python trader_sentiment_analysis.py
📊 Outputs
CSV: trader_sentiment_analysis.csv – Processed dataset with rolling correlation

PNG: trader_sentiment_corr.png – Visualization of PnL vs Sentiment correlation

🔍 Insights Example
Traders tend to over-leverage during greed phases, leading to higher PnL variance

Negative correlation between sentiment and profitability during fear phases — contrarian trading may outperform

Consistent positive correlation during greed phases — momentum strategies may work better

📌 Next Steps
Include additional market sentiment sources (e.g., news sentiment, social media data)

Build a predictive model to forecast PnL probability based on sentiment shifts

Expand analysis to multiple assets

