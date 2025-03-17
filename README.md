# J/K Momentum Trading Strategy on NIFTY 50 📈

This project implements a **J/K Momentum Trading Strategy** on NIFTY 50 stock returns, focusing on **Winner-Loser portfolio analysis**(momentum spread)  to understand momentum effects in the Indian market. 

The strategy identifies "Winners" and "Losers" based on historical performance and evaluates the profitability of a **long-short momentum strategy** using combinations of **formation (J)** and **holding (K)** periods.

---

## 🚀 **Features**

- **Fully modular and reproducible Jupyter Notebook**.
- Analyze multiple J and K combinations (Formation & Holding periods).
- Calculate **Winner and Loser portfolio returns**.
- Analyze **Winner-Loser spread** to capture momentum profit.
- Summary matrix for all J/K combinations.
- Automatically identify **best performing J/K combination**.
---

## 📊 **J/K Momentum Strategy Overview**

1. **Formation Period (J)**: Select top/bottom performers based on J months of past returns.
2. **Holding Period (K)**: Hold Winner and Loser portfolios for K months.
3. **Winner Portfolio**: Top 50 stocks.
4. **Loser Portfolio**: Bottom 50 stocks.
5. **Spread**: Difference between average returns of Winner and Loser portfolios.
6. **Interpretation**: Positive spread = momentum works, Negative spread = possible momentum reversal.

---


