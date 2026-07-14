# Quantitative Risk & Macro Models

Welcome to my quantitative research repository. This project bridges the gap between macroeconomic paradigms, derivative engineering, and market risk metrics using advanced data-driven solutions.

## 🎛️ Repository Structure

*   **`01_Fixed_Income_and_Rates`**: Macaulay/Modified Duration metrics, convexity tracking, and zero-coupon curve bootstrapping.
*   **`02_Risk_Analytics_VaR_ES`**: Dynamic European option pricing (Black-Scholes), Greek sensitivity analytics (Delta/Gamma), and historical/parametric Value-at-Risk (VaR) / Expected Shortfall (ES) models.
*   **`03_Portfolio_Optimization`**: Markowitz Efficient Frontier simulations and risk budgeting allocation based on marginal risk contributions.
*   **`04_Market_Plumbing_Simulations`**: Multilateral netting algorithms for CCPs and liquidity drag simulations under Basel III/CSA frameworks.

---

## 🚀 Highlight: Option Pricing & Delta Convergence (Folder `02`)

This module combines real-time volatility estimation with an analytical Black-Scholes pricing engine to model hedging constraints.

### Analytical Formulae Implemented
For a European Call ($C$) and Put ($P$):
$$C = S_t N(d_1) - K e^{-r T} N(d_2)$$
$$\Delta_{\text{Call}} = N(d_1), \quad \Gamma = \frac{N'(d_1)}{S_t \sigma \sqrt{T}}$$

### Delta Edge-Case Convergence
As the option approaches expiration ($T \to 0$), the Delta profile sharpens into a step function, creating significant Gamma risk for at-the-money options ($S \approx K$):

![Delta Convergence](02_Risk_Analytics_VaR_ES/plots/delta_convergence.png)

---

## 🛠️ Quick Start & Installation

1. **Clone the repository**:
   ```bash
   git clone [https://github.com/Rakooooo/Quantitative-Risk-and-Macro-Models.git](https://github.com/Rakooooo/Quantitative-Risk-and-Macro-Models.git)
   cd Quantitative-Risk-and-Macro-Models
Install dependencies:

Bash
pip install -r requirements.txt
Run the Volatility-Option pipeline:

Bash
python 02_Risk_Analytics_VaR_ES/main_simulation.py
