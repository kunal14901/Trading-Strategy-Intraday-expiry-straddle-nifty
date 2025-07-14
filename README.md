NIFTY Expiry Straddle Strategy v3.0
====================================

A sophisticated backtesting framework for NIFTY options straddle strategies featuring:

- Realistic option price simulation using Black-Scholes
- Dynamic volatility regime detection
- Advanced risk management
- Event-driven trade execution

🌟 Key Features
---------------

### 📈 Realistic Market Simulation

```python
# Dynamic IV calculation
def calculate_realistic_iv(self, spot_price, time_to_expiry_hours, market_sentiment=0):
    base_iv = 0.12 + np.random.normal(0, 0.02)
    time_multiplier = 3.5 if time_to_expiry_hours = 45:  # Time exit
        return True, "TIME_EXIT"
```

🏗️ Architecture
---------------

```mermaid
graph TD
    A[YFinance Data] --> B[Volatility Simulation]
    B --> C[Option Pricing]
    C --> D[Strategy Engine]
    D --> E[Risk Management]
    E --> F[Backtest Analysis]
```

📊 Performance Metrics (Jan-Feb 2024)
-------------------------------------

| Metric        | Value   |
|---------------|---------|
| Total Trades  | 4       |
| Win Rate      | 75%     |
| Avg P&L       | ₹584    |
| Sharpe Ratio  | 0.86    |
| Max Drawdown  | ₹1086   |

**Volatility Regime Performance:**

```python
regime_stats = results.groupby('volatility_regime').agg({
    'Trades': 'count',
    'Avg_PnL': 'mean',
    'Win_Rate': lambda x: sum(x)/len(x)
})
```

🚀 Quick Start
--------------

1. **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

2. **Run backtest:**
    ```bash
    python main.py --start 2024-01-01 --end 2024-02-29
    ```

3. **Analyze results:**
    ```python
    backtester = ImprovedStraddleBacktester()
    backtester.analyze_improved_results()
    ```

📌 Strategy Rules
-----------------

### Entry Conditions

```python
ENTRY_CONDITIONS = {
    'max_iv': 0.20,          # IV threshold
    'min_premium': 3.0,      # Minimum combined premium
    'entry_time': '12:00',   # Optimal entry time
    'min_expiry_hours': 1.5  # Time buffer
}
```

### Exit Conditions

```python
EXIT_CONDITIONS = {
    'profit_target': 0.4,    # 40% of premium
    'stop_loss': 1.8,        # 180% of premium
    'max_hold_minutes': 45   # Time limit
}
```

📚 Documentation Structure
--------------------------

```
docs/
├── API_REFERENCE.md       # Class/method documentation
├── STRATEGY_LOGIC.md      # Detailed trading rules
└── DATA_MODEL.md          # Dataset specifications
```

🛠️ Development Roadmap
-----------------------

- [x] Implement volatility regimes
- [x] Add dynamic position sizing
- [ ] Live trading integration
- [ ] Multi-expiry portfolio backtesting

📫 Contact
----------

For strategy questions or contributions:

- 📧 iknir14901@gmail.com
- 🔗 LinkedIn: kunal-kumar-9aa708200
- 🐛 GitHub: kunal14901
