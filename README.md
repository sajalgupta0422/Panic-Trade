# Panic Trade → Math: 1DTE Put Pricing with Risk Aversion

This repo contains the notebook behind my blog post **“From Panic Trade to Math: Choosing a 1DTE Put with Risk Aversion.”** It’s a small, practical experiment: if you’re going to take a short-dated options bet, can you choose a *less bad* entry price using risk-aware decision rules instead of vibes?

The notebook simulates next-day underlying prices with a one-step lognormal model (GBM step), maps those outcomes to next-day put values using Black–Scholes as a consistent baseline, and then evaluates entry prices using:

- **Probability of profit** via quantiles of the simulated next-day option value distribution
- **Outcome distributions** (profit per contract) to highlight skew and “mean vs median” behavior
- **Breakeven barrier** The Dynamic Breakeven Barrier

where $\Pi$ is profit per contract and $A$ is a risk-aversion parameter.

## What’s in here
- A single notebook that generates:
  - Put value vs underlying (grid + Monte Carlo)
  - Profit distribution / histogram
  - CE curves for different risk-aversion settings
- Figures exported for the blog post

## How to run
1. Create an environment (conda or venv)
2. Install dependencies:
   ```bash
   pip install numpy scipy matplotlib pandas
