# Twitter Sentiment Investing Strategy

## Overview
This project implements a **quantitative investment strategy** based on Twitter sentiment and engagement data. The core idea is to identify stocks with high social media engagement and sentiment, and construct a portfolio that is rebalanced **monthly** based on these metrics.  

By analyzing **Twitter activity** (likes, comments, posts, impressions) and calculating an **engagement ratio**, the strategy aims to select stocks that show strong market attention and potential momentum. The performance of the portfolio is then compared with **NASDAQ/QQQ** to evaluate the strategy's effectiveness.  

---

## Features & Highlights

- **Twitter Sentiment Analysis**: Uses engagement metrics to quantify market interest in specific stocks.  
- **Monthly Portfolio Selection**: Top 5 stocks with the highest engagement ratio are selected each month.  
- **Portfolio Returns**: Calculates daily log returns for selected stocks and compares them with NASDAQ/QQQ benchmark.  
- **Cumulative Returns Visualization**: Plots the cumulative returns over time for the strategy versus the market.  
- **Data Filtering**: Removes stocks with low social media activity to focus on significant signals.  

---

## Tech Stack

- **Python Libraries**: `pandas`, `numpy`, `matplotlib`, `yfinance`  
- **Data Source**: Twitter sentiment CSV data (`sentiment_data.csv`) and Yahoo Finance stock prices  
- **Visualization**: Matplotlib for cumulative return plotting  

---

## How It Works

1. **Load and Preprocess Data**  
   - Load Twitter sentiment dataset  
   - Convert dates to datetime format  
   - Calculate **engagement ratio** (`twitterComments/twitterLikes`)  
   - Filter stocks with low activity  

2. **Aggregate Monthly Metrics**  
   - Compute **average engagement ratio** for each stock per month  
   - Rank stocks cross-sectionally based on engagement  

3. **Select Top Stocks**  
   - Choose the **top 5 stocks per month**  
   - Adjust the portfolio start date to the beginning of the next month  

4. **Download Stock Prices**  
   - Use `yfinance` to fetch historical adjusted close prices for selected stocks  

5. **Calculate Portfolio Returns**  
   - Compute daily log returns  
   - Calculate **monthly rebalanced portfolio returns**  

6. **Benchmark Comparison**  
   - Download NASDAQ/QQQ prices  
   - Compare strategy returns with benchmark returns  

7. **Visualize Strategy Performance**  
   - Plot **cumulative returns** over time to evaluate performance  

---

## Usefulness

- **For Investors**: Provides insights into which stocks are trending positively on social media, helping with short-term momentum strategies.  
- **For Analysts**: Useful for studying correlations between social media engagement and stock returns.  
- **For Quantitative Researchers**: Serves as a base for integrating alternative data sources (social media sentiment) into algorithmic trading strategies.  

---

## Benefits

- Helps identify **stocks with high retail investor interest**  
- Can outperform traditional benchmarks in certain periods  
- Simple and modular strategy that can be **extended with additional signals** (e.g., sentiment polarity, news data)  
- Fully automated pipeline for portfolio creation and performance tracking  

---

## Project Highlights

- **Dynamic Portfolio Rebalancing**: Adjusts top 5 stocks each month based on live Twitter engagement data.  
- **Cross-Sectional Ranking**: Uses relative engagement ranking for fair comparison across all stocks.  
- **Performance Comparison**: Visualizes strategy versus NASDAQ/QQQ to evaluate real-world viability.  

---

## How to Run

1. Clone the repository and place your **Twitter sentiment CSV** in the `data` folder.  
2. Install the required Python libraries:  

```bash
pip install pandas numpy matplotlib yfinance
