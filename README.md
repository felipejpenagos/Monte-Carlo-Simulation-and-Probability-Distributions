# Monte Carlo Simulation – Overview

This project uses a Monte Carlo simulation to estimate the probability that:

Y = sin(X₁) + sqrt(X₂) - exp(-X₃) - 2 > 0

where X₁, X₂, and X₃ are random variables with different probability distributions.

---

## What We Did

1. **Defined inputs**:  
   - X₁: Normal (mean=6, std=2)  
   - X₂: Lognormal (median=2, cov=0.3)  
   - X₃: Rayleigh (scale=1)

2. **Generated 1,000 random samples**  
3. **Evaluated Y** for each sample  
4. **Estimated failure probability** as `P(Y > 0)`  
5. **Visualized** histograms and CDFs

---

## Why Monte Carlo?

Monte Carlo was useful here because the function is nonlinear and difficult to analyze analytically. It allowed us to numerically estimate the probability of failure using random sampling.

---

## Libraries Used

- **NumPy** – random sampling and math  
- **SciPy** – probability distributions (normal, lognormal, Rayleigh)  
- **Matplotlib** – visualizations (PDFs, histograms, CDFs)
