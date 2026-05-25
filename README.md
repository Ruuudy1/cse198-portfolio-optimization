# Portfolio Optimization - CSE 198 Week 7

**Rudy Osuna - UC San Diego - CSE 198**

A seminar on modern portfolio theory: why the textbook version breaks in practice, how linear algebra reshapes the problem, and how options unlock volatility as a tradable asset.

---

## See Full Lecture Animations

[![Watch on YouTube](https://img.youtube.com/vi/PDvTe4oJhHQ/maxresdefault.jpg)](https://www.youtube.com/watch?v=PDvTe4oJhHQ)

---

## Seminar Flow

### 1 - Modern Portfolio Theory: the promise
Mean-variance optimization, the efficient frontier, and Tobin's two-fund separation theorem. Every rational investor holds the same tangency portfolio; only the cash fraction changes.

### 2 - Why the inputs are wrong
Expected returns are nearly impossible to estimate reliably. Volatility treats upside and downside symmetrically, penalizes good variance, and assumes returns are Gaussian. NVDA's tail events shatter that assumption. Correlations collapse to 1 in a crisis, erasing diversification exactly when you need it most.

### 3 - Fixing the inputs and using a better objective
- Non-stationarity: NVDA's 2014-15 regime vs. 2023-24 AI-era regime are completely different distributions; a single mean estimate is meaningless.
- Sortino ratio: penalise only downside deviation, not total volatility.
- Probabilistic Sharpe Ratio (PSR): a high Sharpe from few fat-tailed observations is not statistical significance. PSR corrects for skew and kurtosis.
- CVaR: optimise the expected loss in the worst tail, not just variance.

### 4 - Reshaping with linear algebra
The covariance matrix decomposes into eigenportfolios, the market's natural risk axes. The Marchenko-Pastur law separates genuine signal eigenvalues from noise. Ledoit-Wolf shrinkage tames the condition number so the inverse covariance matrix stays stable. Risk is decomposed in the eigen-basis to show exactly how much variance each factor contributes.

### 5 - Statistical validation of parameters
The PSR formula tests whether an observed Sharpe ratio is statistically distinguishable from a benchmark, accounting for the fat tails and skew that inflate the sampling variance of Sharpe.

### 6 - Options portfolio optimization (extra)
Options make P&L nonlinear: dPnL is approximately Delta times dS plus one-half Gamma times dS squared plus Vega times d-sigma plus Theta times dt. Greeks define the local shape of the payoff. An end-to-end pipeline covers universe construction, scenario generation, a repricing matrix, a CVaR objective, Greek constraints, solving, and dynamic hedging.

---

## Preview - Options Pipeline

![Options pipeline animation](options-pipeline.gif)

---

## Resources

| File | Description |
|------|-------------|
| [lecture-notes.pdf](lecture-notes.pdf) | Full written lecture notes with derivations |
| [slides.pdf](slides.pdf) | Slide deck used in the seminar |

---

## Animations

All 19 scenes were built with [Manim Community](https://www.manim.community/) (3Blue1Brown's engine) at 3840x2160 / 60 fps.
