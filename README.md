# Portfolio Optimization using Monte Carlo Simulation and Mathematical Optimization

This project implements portfolio optimization techniques to maximize the Sharpe ratio, minimize volatility, and create efficient portfolios based on historical stock data. It uses Monte Carlo simulation and mathematical optimization methods to achieve these goals.

## Features

1. **Data Collection**: Fetches historical stock prices using the `yfinance` library.
2. **Return Calculation**:
   - Supports arithmetic and logarithmic returns.
   - Allows resampling for different time periods (e.g., monthly, daily).
3. **Portfolio Metrics**:
   - Calculates portfolio returns, variance, and standard deviation.
   - Computes mean returns and covariance matrix.
4. **Monte Carlo Simulation**:
   - Simulates random portfolio weights to find portfolios with the highest Sharpe ratio and minimum volatility.
5. **Mathematical Optimization**:
   - Maximizes Sharpe ratio using the SLSQP optimization method.
   - Minimizes portfolio variance for given constraints.
   - Generates efficient portfolios for specific target returns.
6. **Visualization**:
   - Plots all simulated portfolios with Sharpe ratio as the color scale.
   - Highlights the portfolio with maximum Sharpe ratio and minimum volatility.

## Libraries Used

- `numpy`
- `pandas`
- `matplotlib`
- `yfinance`
- `scipy.optimize` (for optimization methods)

## Setup and Installation

1. Clone the repository.
   ```bash
   git clone https://github.com/your-repo/portfolio-optimization.git
   ```
2. Navigate to the project directory.
   ```bash
   cd portfolio-optimization
   ```
3. Install required libraries.
   ```bash
   pip install numpy pandas matplotlib yfinance scipy
   ```

## Usage

### 1. Fetch Historical Data
Modify the `symbols` list to include the stock tickers you want to analyze.

```python
symbols = ['AAPL', 'MSFT', 'GOOGL']
```

### 2. Calculate Returns
Choose between arithmetic or logarithmic returns and resample the data if needed.

```python
monthly_ret_arith = calc_returns(price_data, resample='BM', ret_type="arithmatic")
```

### 3. Monte Carlo Simulation
Run simulations to generate random portfolio weights and evaluate Sharpe ratios, returns, and volatility.

```python
num_iter = 500000
# Monte Carlo simulation logic in the script
```

### 4. Optimization
Use optimization functions to find portfolios with:
- Maximum Sharpe ratio
- Minimum variance
- Efficient portfolio for a target return

```python
opt_sharpe, opt_weights, opt_return, opt_variance, opt_std = optimize_sharpe_ratio(mean_returns, cov_matrix)
```

### 5. Visualize Results
Generate scatter plots of portfolios with annotations for key portfolios.

```python
plt.scatter(porfolio_var_list, porfolio_ret_list, c=stat['Sharpe ratio'], cmap='plasma')
```

## Outputs

- Annualized portfolio returns, volatility, and Sharpe ratio for key portfolios.
- Weights for portfolios with maximum Sharpe ratio and minimum volatility.
- Efficient portfolios for given target returns.

## Example Results

### Portfolio with Maximum Sharpe Ratio:
- **Sharpe Ratio**: `2.45`
- **Annual Return**: `20.5%`
- **Annual Volatility**: `10.3%`
- **Weights**: 
  - AAPL: `40%`
  - MSFT: `30%`
  - GOOGL: `30%`

### Portfolio with Minimum Volatility:
- **Sharpe Ratio**: `1.8`
- **Annual Return**: `15.2%`
- **Annual Volatility**: `8.0%`
- **Weights**:
  - AAPL: `20%`
  - MSFT: `50%`
  - GOOGL: `30%`
