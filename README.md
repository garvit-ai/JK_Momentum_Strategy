# 📈 J/K Momentum Trading Strategy on NIFTY

## 🔑 Overview

This project implements **J/K Momentum Trading Strategy** applied to NIFTY stock returns. The strategy selects 50 stocks from the given dataset and then form top decile (loser portfolio) and bottom decile (winner portfolio) based on past cumulative returns and evaluates their performance over a holding period. The entire pipeline is modularized, allowing flexibility to choose different J (formation) and K (holding) periods while comparing the results with the NIFTY benchmark.

Features

- **Historical Data Processing**: Load and filter NIFTY stock returns and index returns.
- **Momentum Strategy Implementation**: Generate winner and loser portfolios dynamically based on J/K periods.
- **Performance Comparison**: Identify the **best J/K pair** based on the spread between winner and loser portfolios.
- **Visualization**: Plot **cumulative return comparison** between Winner-Loser spread and NIFTY index.
- **Export Results**: Save the final strategy output of the best J/K to an Excel file.

## Prerequisites

- **Python 3.6+**
- **Jupyter Notebook** (or JupyterLab)
- Required Python libraries:
  - `pandas`
  - `matplotlib`
  - `openpyxl` (for Excel export)
  - `itertools` (standard library, no installation needed)
---

## 📂 How to Clone and Run the Project

1. **Create a folder** where you want to keep this project.

2. **Open terminal (bash)** in that folder:
   - Right-click inside the folder and select "Open in Terminal" or "Open Git Bash here".

3. **Clone this repository** by running the following command in the terminal:

```git clone https://github.com/garvit-ai/JK_Momentum_Strategy.git
```

After cloning the repository, ensure:

- **Update the file path**  of the dataset in section 2 load and filter data

```
file_path = 'path/to/Monthly_Log_Returns(prcnt) 2002-2024.xlsx'
```

You can customize the start and end dates, and adjust the J/K combinations directly in the notebook as per your requirement:

in section 2 load and filter data
```
custom_start_date = pd.to_datetime("2002-01-01")
```
```
custom_end_date = pd.to_datetime("2024-12-31")
```
in last seciton running engine
```
J_list, K_list = [6], [3]  # Modify these lists as desired
```


---
## 🧩 Modules and Functions

| Module Name                                           | Purpose                                                              |
|------------------------------------------------------|----------------------------------------------------------------------|
| `load_and_filter_data(file_path, sheet_name, start_date, end_date)` | Load and filter stock/index returns for a user-specified date range. |
| `run_jk_strategy(df, J, K, custom_end_date)`     | Generate winner and loser portfolios based on J (formation) and K (holding) periods. |
| `calculate_monthly_returns(df, portfolios)`     | Calculate monthly returns for winner and loser portfolios independently. Returns separate DataFrames. |
| `calculate_and_display_summary(winner_df, loser_df, J, K)` | Compute and return average winner, loser returns, and spread for a specific J/K pair. |
| `export_best_jk_results_to_excel(final_df, best_J, best_K)` | Export monthly returns (winner, loser, spread) of the best J/K combo to an Excel file. |
| `plot_cumulative_returns_for_best_jk(final_df, nifty_df, best_J, best_K)` | Plot cumulative returns of Winner-Loser spread vs NIFTY index for the best J/K combination. |
| `Running Engine (J/K Loop + Result Analysis)` | Runs the entire J/K strategy across combinations, stores results, finds optimal J/K, visualizes, and exports output. |

---

## ⚙️ Workflow

1. **Data Loading and Filtering**:
   - Load historical **monthly log returns** of NIFTY stocks and NIFTY index.
   - Filter based on a custom date range (e.g., `2002-01-01` to `2024-12-31`).

2. **J/K Strategy Application**:
   - Iterate over predefined lists of J (formation periods) and K (holding periods).
   - For each J/K pair:
     - Form **Winner and Loser portfolios**.
     - Calculate **monthly average returns**.
     - Compute **average return spread** (Winner minus Loser).

3. **Performance Summary**:
   - Store all J/K results in a summary table.
   - **Identify the best J/K combination** based on the highest return spread.

4. **Portfolio Reuse for Best J/K**:
   - Reuse stored portfolios for best J/K pair to avoid recomputing.
   - Calculate detailed monthly return performance for the best J/K.

5. **Visualization**:
   - Plot **cumulative return graph** comparing Winner-Loser spread vs NIFTY index to analyze relative performance over time.

6. **Result Export**:
   - Export detailed monthly returns and spread of the best J/K strategy to an Excel file with a timestamped filename for record keeping.

---


## Example Output


![Winner-Loser vs NIFTY Cumulative Returns](/output_image/output%201.png)

![Portfolio Summary Table](/output_image/output%202.png)


## 📄 Research Paper Reference  

This project is inspired by and based on the methodology discussed in:  

> **Jegadeesh, N., & Titman, S. (1993).**  
> *Returns to Buying Winners and Selling Losers: Implications for Stock Market Efficiency.*  
Stable URL: http://www.jstor.org/stable/2328882


---

## 📬 Contact

For queries, collaborations, or improvements, feel free to reach out garrvitb@gmail.com

