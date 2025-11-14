# Monte Carlo Simulation – Python Adaptation

This repository contains a small introductory example of Monte Carlo Simulation (MCS) adapted from the original MATLAB script **MCS_intro.m** written by **Prof. H.P. Gavin** (Duke University, CEE 251L – *Uncertainty, Design, and Optimization*).

The goal is to illustrate how uncertainty in several random variables propagates through a nonlinear function.

---

## Problem Setup

We estimate the probability that the function

\[
Y = \sin(X_1) + \sqrt{X_2} - e^{-X_3} - 2
\]

exceeds zero. The input random variables are:

- \( X_1 \sim \mathcal{N}(6, 2) \)
- \( X_2 \sim \text{Lognormal}(\text{median}=2,\ \text{cov}=0.3) \)
- \( X_3 \sim \text{Rayleigh}(\sigma=1) \)

---

## Method

1. Draw \( N = 1000 \) independent samples from each distribution.  
2. Compute \( Y^{(i)} = \sin(X_1^{(i)}) + \sqrt{X_2^{(i)}} - e^{-X_3^{(i)}} - 2 \).  
3. Estimate the probability \( P(Y > 0) \) empirically:

\[
\widehat{P}(Y > 0) = \frac{1}{N}\sum_{i=1}^N \mathbf{1}\{ Y^{(i)} > 0 \}.
\]

4. Plot histograms and empirical CDFs of the inputs and of the resulting distribution of \(Y\).

This demonstrates the basic mechanics of Monte Carlo Simulation:  
**sample → evaluate → aggregate statistics**.

---

## Notes

- This notebook is intended purely as an instructional translation from MATLAB to Python.  
- All distribution parameter conversions (e.g., lognormal median–cov to scale/shape) follow standard formulas used in CEE 251L.  
- Original MATLAB material © H.P. Gavin, Duke University.
