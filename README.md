# Quantitative Risk & Derivatives Engineering

Python implementations of derivative pricing engines, econometric volatility modeling, and statistical learning applied to credit and market risk.

---

## 🎛️ Repository Structure

* **`01_Derivatives_Pricing`**: Vectorized Black-Scholes analytical engine, Greek sensitivity mapping ($\Delta$, $\Gamma$, $\nu$, $\Theta$), and discrete dynamic hedging simulations.
* **`02_Time_Series_Econometrics_VaR`**: Asymmetric volatility modeling (EGARCH-$t$, IGARCH), multivariate VAR(1) filtering on mega-cap tech/semiconductor equities (ASML, NVDA), and dynamic risk tunnels.
* **`03_Predictive_Data_Science`**: Statistical credit and liquidity classification using penalized regression (LASSO $L_1$), Random Forest, and Gradient Boosting with TreeSHAP explainability.

---

## 🚀 Module Highlights

### 1. Vectorized Option Pricing & Hedging Error (`01_Derivatives_Pricing`)
* **Vectorized Analytical Solver**: Implements closed-form Black-Scholes pricer and primary Greeks in sub-millisecond execution via NumPy broadcasting.
* **Delta Convergence & Gamma Risk**: Models the convergence of the Delta profile toward a Heaviside step function as $T \to 0$, quantifying the ATM Gamma explosion.
* **Discrete Hedging Tracking Error**: Simulates discrete rebalancing constraints across geometric Brownian motion paths to quantify P&L variance against continuous-time theoretical replication.

### 2. Tech & Semiconductor Volatility Pipeline (`02_Time_Series_Econometrics_VaR`)
* **Asymmetric Volatility Dynamics**: Calibrates EGARCH($p,q$) specifications under Student-$t$ distributed innovations to capture leverage effects and negative news shocks on ASML and NVDA.
* **Multivariate Residual Filtering**: Fits a VAR(1) system to DeGARCHed return series. Demonstrates absence of lagged cross-asset predictability while isolating high contemporaneous residual correlation ($\rho = 0.57$).
* **Out-of-Sample Risk Tunnels**: Evaluates 1-step-ahead dynamic confidence intervals, capturing structural price contractions with zero local violations.

### 3. Credit & Liquidity Analytics (`03_Predictive_Data_Science`)
* **Parsimonious Feature Selection**: Grid-searches optimal $L_1$ penalty ($C = 166.81$) via 5-fold cross-validation to eliminate non-predictive features and ensure model explainability.
* **Ensemble Benchmarking**: Compares Random Forest (84.8% accuracy, 87.6% recall) and Gradient Boosting against linear baselines.
* **TreeSHAP Attribution**: Computes non-linear marginal feature importances, identifying structural behavioral drivers while isolating potential look-ahead variables.

---

## 🛠️ Quick Start

```bash
git clone [https://github.com/Rakooooo/Quantitative-Risk-and-Macro-Models.git](https://github.com/Rakooooo/Quantitative-Risk-and-Macro-Models.git)
cd Quantitative-Risk-and-Macro-Models
pip install -r requirements.txt
python 01_Derivatives_Pricing/main_simulation.py
