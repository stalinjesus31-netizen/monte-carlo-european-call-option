# Monte Carlo Simulation for European Call Option Pricing

📄 **[View Full Report](https://stalinjesus31-netizen.github.io/monte-carlo-european-call-option/)**

Pricing a European call option on **Rheinmetall AG (RHM.DE)** using Monte Carlo simulation under the risk-neutral measure, with comparison against the Black-Scholes analytical solution and implementation of three variance reduction techniques.

---

## Methods

**Baseline Monte Carlo** — simulates 1,000,000 asset price paths under Geometric Brownian Motion and estimates the option price as the discounted average payoff.

**Variance Reduction Techniques:**
| Method | Std. Error Reduction (vs. Baseline) |
|---|---|
| Antithetic Variates | ~0.3–0.7% |
| Control Variates | ~55–70% |
| Importance Sampling | ~65% |

---

## Model Parameters

| Parameter | Value | Description |
|---|---|---|
| $S_0$ | €1,736 | Rheinmetall AG spot price (29 Oct 2025) |
| $r$ | 3.5% | Risk-free rate (Euribor 3M, Oct 2025) |
| $\sigma$ | 0.40 | Annualised historical volatility (2024–2025) |
| $T$ | 0.25 | Time to maturity (3 months) |
| $N$ | 1,000,000 | Number of simulations |

Three strike prices are analysed: OTM ($1.1 \times S_0$), ATM ($S_0$), and ITM ($0.9 \times S_0$).

---

## Results

All methods converge to the Black-Scholes theoretical price, with deviations below €0.31 across all strikes. Control Variates and Importance Sampling reduce the standard error by over 55%, achieving equivalent precision with significantly fewer simulations.

---

## Repository Structure

```
├── monte_carlo_call_option.Rmd   # Full analysis: theory, simulation, results, plots
├── index.html                    # Rendered report (served via GitHub Pages)
├── apresentacao.pdf              # Slides with theoretical framework (GBM, Black-Scholes)
└── README.md
```

---

## How to Run

1. Open `monte_carlo_call_option.Rmd` in RStudio
2. Install dependencies if needed:
```r
install.packages(c("ggplot2", "scales", "knitr"))
```
3. Click **Knit** to render as HTML or PDF

> Note: the simulation runs 1M paths per method. Chunks marked `cache=TRUE` will be cached after the first render.

---

## Topics

`monte-carlo` `options-pricing` `black-scholes` `variance-reduction` `stochastic-processes` `quantitative-finance` `R` `geometric-brownian-motion`
