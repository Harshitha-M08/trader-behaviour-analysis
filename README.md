# 📊 Trader Behavior Insights: Market Sentiment vs Performance

## 🔍 Objective

This project analyzes the relationship between Bitcoin market sentiment (Fear, Greed, Neutral) and trader behavior using historical trading data.

The goal is to uncover how **market psychology influences trading decisions, risk-taking, and profitability**, and to derive insights that can improve trading strategies.

---

## 📁 Datasets Used

### 1. Bitcoin Market Sentiment Dataset

* Date
* Sentiment Classification (Fear / Greed / Neutral)

### 2. Historical Trader Data (Hyperliquid)

* Account
* Execution Price
* Trade Size (USD / Tokens)
* Side (Buy/Sell)
* Timestamp
* Closed PnL

---

## ⚙️ Data Preprocessing

* Standardized column names to ensure consistency
* Converted raw timestamps (milliseconds) into structured datetime format
* Aligned both datasets at **daily granularity** for accurate merging
* Normalized sentiment categories (Extreme Fear → Fear, Extreme Greed → Greed)
* Removed invalid and missing records to maintain data integrity

Result:

* ~184,000+ trades successfully aligned with sentiment data

---

## ⚙️ Feature Engineering

To move beyond raw data, behavioral features were engineered:

* **Profit** → Trade outcome (PnL)
* **Win Indicator** → Binary success metric
* **Trade Frequency** → Activity level per trader per day
* **Size Category** → Trade segmentation (small / medium / large)
* **Risk Proxy** → Trade Size × Trade Frequency
  *(used as a substitute for leverage to estimate risk exposure)*
* **Sentiment Shift** → Captures transition between market states

---

## 📊 Key Insights

### 1. Market Sentiment Drives Profitability

* Highest profitability and win rate observed during **Greed phases**
* Indicates that bullish conditions provide favorable trading environments

> Traders perform best when market direction is clear and positive.

---

### 2. Fear Triggers Overtrading Behavior

* Trade frequency and risk exposure peak during **Fear phases**
* Significantly higher activity compared to Greed

> This suggests **panic-driven overtrading**, where traders react emotionally rather than strategically.

---

### 3. Risk Does Not Equal Performance

* Highest risk proxy observed during Fear
* However, profitability remains lower than Greed

> Increased activity and exposure do not translate into better outcomes, highlighting inefficient trading behavior.

---

### 4. Neutral Markets Are the Hardest to Trade

* Lowest profit and win rate observed during Neutral sentiment

> Traders struggle in directionless markets, indicating dependence on strong sentiment signals.

---

## 🧠 Advanced Analysis

### 🔄 Sentiment Shift Behavior

* Direct Fear → Greed transitions were not observed, suggesting gradual sentiment evolution through intermediate states

> Market transitions are not abrupt, indicating delayed or stepwise trader reactions.

---

### 💰 Smart Money vs Weak Traders

#### Smart Traders:

* Significantly increase activity during Fear phases
* Maintain stable win rates across all conditions

#### Weak Traders:

* Low participation and inconsistent performance
* Sharp performance drop in Neutral markets

> **Key Insight:**
> Top traders exhibit **contrarian and disciplined behavior**, while weak traders are reactive and inconsistent.

---

### 🤖 Trader Clustering (Behavior Profiling)

Three distinct trader profiles were identified:

* **Cluster 0 (Balanced Performers):**
  High profitability with controlled risk

* **Cluster 1 (Overtraders):**
  Extremely high exposure with lower returns → inefficient strategy

* **Cluster 2 (Conservative Traders):**
  Lower risk with stable but moderate performance

> Overtrading emerges as a key factor behind poor performance.

---

## 🧠 Strategic Recommendations

Based on the analysis:

* ✔ Avoid excessive trading during Fear phases
* ✔ Use contrarian strategies when market panic is high
* ✔ Reduce activity in Neutral (uncertain) markets
* ✔ Focus on consistency rather than high-risk exposure

---

## 🚀 Conclusion

This analysis demonstrates that **trader behavior is heavily influenced by market sentiment**, with emotional reactions often leading to suboptimal outcomes.

Successful traders differentiate themselves through:

* Discipline
* Timing
* Controlled risk exposure

Rather than reacting emotionally to market conditions.

---

## 🛠️ Tech Stack

* Python (Pandas, NumPy)
* Data Visualization (Matplotlib, Seaborn)
* Machine Learning (KMeans Clustering)
* Google Colab

---

## 📌 Future Work

* Incorporate real-time sentiment signals
* Build predictive models for trade profitability
* Develop automated trading strategy recommendations
