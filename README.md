# Portfolio Optimization Toolkit

A Python-based portfolio optimization system implementing Modern Portfolio Theory (MPT) for calculating efficient frontiers, optimal allocations, and risk-return metrics. Designed for financial analysis and investment strategy development.

## Key Features

### 🔍 Core Optimization Functions
- *Maximum Sharpe Ratio Portfolio*: Optimal risk-adjusted returns
- *Minimum Variance Portfolio*: Lowest possible risk configuration
- *Efficient Frontier Generator*: Risk-return optimal portfolios
- *Annualized Performance Metrics*: Standard deviation and returns

### 📊 Streamlit Integration
- Interactive web interface for portfolio analysis
- Visual allocation displays
- Performance metric comparisons

## 📥 Installation

pip install pandas numpy scipy matplotlib streamlit


## 🛠 Usage

### Basic Implementation

# Import required functions
from portfolio_optimizer import (portfolio_annualised_performance,
                                max_sharpe_ratio,
                                min_variance,
                                efficient_return,
                                efficient_frontier,
                                display_calculated_ef_with_random)

# Load financial data
stock_data = pd.read_csv('your_stock_data.csv')
returns = stock_data.pct_change().dropna()
mean_returns = returns.mean()
cov_matrix = returns.cov()

# Calculate optimal portfolios
risk_free_rate = 0.02  # Example risk-free rate
max_sharpe_port = max_sharpe_ratio(mean_returns, cov_matrix, risk_free_rate)
min_vol_port = min_variance(mean_returns, cov_matrix)


### Streamlit Web App

streamlit run your_script_name.py


## 📈 Key Functions Explained

### max_sharpe_ratio()
- *Purpose*: Find optimal risk-adjusted portfolio
- *Inputs*: 
  - Mean returns (pd.Series)
  - Covariance matrix (pd.DataFrame)
  - Risk-free rate (float)
- *Output*: Optimized weight allocations

### min_variance()
- *Purpose*: Identify lowest volatility portfolio
- *Inputs*:
  - Mean returns
  - Covariance matrix
- *Output*: Minimum volatility weights

### efficient_frontier()
- *Purpose*: Generate Markowitz bullet curve
- *Inputs*:
  - Target returns range
  - Mean returns
  - Covariance matrix
- *Output*: Collection of efficient portfolios

## 📋 Example Output

# Sample portfolio allocations
print("Max Sharpe Allocation:")
print(max_sharpe_allocation)

print("\nMinimum Volatility Allocation:")
print(min_vol_allocation)


## ⚙ Technical Implementation
- *Optimization Algorithm*: Sequential Least Squares Programming (SLSQP)
- *Constraints*:
  - Full investment (∑ weights = 1)
  - No short selling (0 ≤ weight ≤ 1)
- *Performance Metrics*:
  - Annualized returns (252 trading days)
  - Annualized volatility

## 📌 Requirements
- Python 3.7+
- NumPy
- SciPy
- Pandas
- Matplotlib
- Streamlit (for web interface)

## ⚠ Disclaimer
This tool provides mathematical optimizations, not financial advice. Past performance ≠ future results. Always conduct thorough due diligence before making investment decisions.
