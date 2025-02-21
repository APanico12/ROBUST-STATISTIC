# Asymptotic Relative Efficiency (ARE) of the Sample Mean vs. Trimmed Mean

## Problem Description

We consider a set of independent and identically distributed (iid) random variables:

$X_1, X_2, ..., X_n \sim N(\mu, \sigma^2)$

where $N(\mu, \sigma^2)$ denotes a normal distribution with mean $\mu$ and variance $\sigma^2$. Our goal is to compare the efficiency of two estimators for $\mu$:

1. **Sample Mean** $\bar{X}$:

   $\bar{X}$ = $\frac{1}{n}$ $\sum_{i=1}^{n}$ $X_i$

2. **Trimmed Mean** $\bar{X}_\alpha$, with a symmetric trimming proportion $\alpha$, which removes the smallest and largest $\alpha n$ values:

   $\bar{X_\alpha}$ = $\frac{1}{n - 2k}$ $\sum_{i=k+1}^{n-k}$ $X_{(i)}$

   where $k = \lfloor \alpha n \rfloor$ and $X_{(i)}$ are the order statistics.

The efficiency of these estimators is measured through the **Asymptotic Relative Efficiency (ARE)**, defined as the ratio of their asymptotic variances:

$\text{ARE}$($\bar{X}$, $\bar{X_\alpha}$) = $\frac{\text{Var}(\bar{X_\alpha)})}{\text{Var}(\bar{X}}$

## Analytical Result

Using standard results for truncated normal moments, the variance of the trimmed mean is given by:

$\text{Var}(\bar{X_\alpha}) = \frac{\sigma^2}{(1 - 2\alpha)^2 n} \left(1 - \frac{z_{1-\alpha} \varphi(z_{1-\alpha}) - z_\alpha \varphi(z_\alpha)}{\Phi(z_{1-\alpha}) - \Phi(z_\alpha)} \right)$

where:
- $\varphi(z)$ is the PDF of the standard normal distribution,
- $\Phi(z)$ is the CDF of the standard normal distribution,
- $z_\alpha = \Phi^{-1}(\alpha)$ and $z_{1-\alpha} = \Phi^{-1}(1 - \alpha)$ are the quantiles of the normal distribution.

Since the variance of the sample mean is:

$\text{Var}(\bar{X}) = \frac{\sigma^2}{n}$,

we obtain the final ARE equation:

$\text{ARE}(\bar{X}, \bar{X_\alpha}) = \frac{1}{(1 - 2\alpha)^2} \left[ 1 +\frac{2Z_{\alpha} \varphi(Z_{\alpha}) }{\Phi(Z_{1-\alpha}) - \Phi(Z_{\alpha})}\right]$

## Monte Carlo Simulation

To validate our analytical result, we conduct a **Monte Carlo simulation** by generating multiple random samples from a normal distribution $N(2, 4)$ and computing both estimators $\bar{X}$ and $\bar{X}_\alpha$.

We set:
- $\mu $= 2, $\sigma$ = 4,
- $\alpha$ = 0.05,
- A large number of simulations to approximate the empirical variance of $\bar{X}_\alpha$ and compare it with the theoretical formula.

The simulation results confirm the accuracy of the derived ARE formula, demonstrating the efficiency loss of the trimmed mean relative to the standard sample mean.

## Conclusion

This study derives and verifies the **Asymptotic Relative Efficiency (ARE)** of the sample mean and the trimmed mean. The theoretical variance matches the empirical variance obtained through simulations, validating the analytical expressions. This analysis is useful in statistical inference, especially when dealing with heavy-tailed distributions where trimming can provide robust estimators.
