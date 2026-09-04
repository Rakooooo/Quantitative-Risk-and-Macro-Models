# Quantitative Risk & Derivatives Engineering

Python implementation of derivative pricing engines, econometric volatility modeling, and statistical learning applied to credit and market risk.

---

## 🎛️ Repository Structure

* **`01_Derivatives_Pricing`**: Vectorized Black-Scholes analytical engine, Greek sensitivity mapping ($\Delta$, $\Gamma$, $\nu$, $\Theta$, $\rho$), Newton-Raphson implied volatility extraction, and Monte Carlo discrete delta-hedging simulations.
* **`02_Time_Series_Econometrics_VaR`**: Asymmetric volatility modeling (EGARCH-$t$, IGARCH), multivariate VAR(1) filtering on mega-cap tech/semiconductor equities (ASML, NVDA), and dynamic risk tunnels.
* **`03_Predictive_Data_Science`**: Statistical credit and liquidity classification using penalized regression (LASSO $L_1$), Random Forest, and Gradient Boosting with TreeSHAP explainability.

---

## 🚀 Module Highlights: Derivatives Pricing & Hedging Engine

### 1. Vectorized Analytical Solver & Greeks
* **Broadcasting Engine**: Computes closed-form Black-Scholes prices and full analytical Greeks ($\Delta, \Gamma, \nu, \Theta, \rho$) in sub-millisecond execution using NumPy vectorization.
* **Implied Volatility Extraction**: Implements a robust Newton-Raphson solver bounded via `np.clip` to prevent negative volatility divergence when processing live market quotes.
* **Live Market Integration**: Pulls nearest-expiry at-the-money option chains via `yfinance`, with built-in bid-ask midpoint fallback for illiquid strikes.

### 2. Discrete Delta-Hedging Tracking Error ("Gamma bleed")
* **Self-Financing Replication:** Seeds the replicating portfolio with the option's actual traded premium ($\Pi_0 = \text{option\_price}$), isolating pure discretization tracking error from capital-bias artifacts.
* **Gamma Explosion ($T \to 0$)**: Simulates geometric Brownian motion paths under the risk-neutral measure to quantify convexity losses during discrete rebalancing intervals.

### 3. Execution Speed Benchmark
Delta computation across a paths $\times$ steps grid, measured on local hardware via `python benchmark.py`:

| Implementation          | 1,000 paths | 10,000 paths | 100,000 paths |
|--------------------------|------------:|-------------:|--------------:|
| Naive Python loop        |    196.5 ms |            — |             — |
| NumPy vectorized         |      6.3 ms |     118.5 ms |    1,209.2 ms |
| **Numba JIT (parallel)** |   **4.6 ms** |     **40.8 ms** |     **510.9 ms** |

*Numba delivers a 1.4x to 2.9x speedup over vectorized NumPy, and up to 43x over a naive Python loop.*

---

## 🛠️ Quick Start

```bash
git clone [https://github.com/Rakooooo/Quantitative-Risk-and-Macro-Models.git](https://github.com/Rakooooo/Quantitative-Risk-and-Macro-Models.git)
cd Quantitative-Risk-and-Macro-Models/01_Derivatives_Pricing
pip install -r requirements.txt
python nvda_options_engine.py
python benchmark.py
