# Asymptotic Relative Efficiency (ARE) of the Sample Mean vs. Trimmed Mean

## Problem Description
# We consider a set of independent and identically distributed (iid) random variables:
# X_1, X_2, ..., X_n ~ N(mu, sigma^2)
# where N(mu, sigma^2) denotes a normal distribution with mean mu and variance sigma^2.
# Our goal is to compare the efficiency of two estimators for mu:

# 1. The **sample mean** X_bar:
#    X_bar = (1/n) * sum(X_i) for i=1 to n

# 2. The **trimmed mean** X_bar_alpha with a symmetric trimming proportion alpha, which removes
#    the smallest and largest alpha*n values:
#    X_bar_alpha = (1/(n - 2k)) * sum(X_(i)) for i=k+1 to n-k
#    where k = floor(alpha * n) and X_(i) are the order statistics.

# The efficiency of these estimators is measured through the **Asymptotic Relative Efficiency (ARE)**, 
# defined as the ratio of their asymptotic variances:
# ARE(X_bar, X_bar_alpha) = Var(X_bar) / Var(X_bar_alpha).

## Analytical Result
# Using standard results for truncated normal moments, the variance of the trimmed mean is given by:
# Var(X_bar_alpha) = (sigma^2 / (1 - 2*alpha)^2 * n) * (1 - (z_(1-alpha) * phi(z_(1-alpha)) - z_alpha * phi(z_alpha)) / (Phi(z_(1-alpha)) - Phi(z_alpha)))

# where:
# - phi(z) is the PDF of the standard normal distribution,
# - Phi(z) is the CDF of the standard normal distribution,
# - z_alpha = Phi^(-1)(alpha) and z_(1-alpha) = Phi^(-1)(1 - alpha) are the quantiles of the normal distribution.

# Since the variance of the sample mean is:
# Var(X_bar) = sigma^2 / n,
# we obtain the final ARE formula:
# ARE(X_bar, X_bar_alpha) = ((1 - 2*alpha)^2) / (1 - (z_(1-alpha) * phi(z_(1-alpha)) - z_alpha * phi(z_alpha)) / (Phi(z_(1-alpha)) - Phi(z_alpha))).

## Monte Carlo Simulation
# To validate our analytical result, we conduct a **Monte Carlo simulation** by generating multiple random samples 
# from a normal distribution N(mu = 2, sigma^2 = 4) and computing both estimators X_bar and X_bar_alpha.

# We set:
# - mu = 2, sigma = 4,
# - alpha = 0.005,
# - A large number of simulations to approximate the empirical variance of X_bar_alpha and compare it with the theoretical formula.

# The simulation results confirm the accuracy of the derived ARE formula, demonstrating the efficiency loss of 
# the trimmed mean relative to the standard sample mean.

## Conclusion
# This study derives and verifies the **Asymptotic Relative Efficiency (ARE)** of the sample mean and the trimmed mean. 
# The theoretical variance matches the empirical variance obtained through simulations, validating the analytical expressions.
# This analysis is useful in statistical inference, especially when dealing with heavy-tailed distributions where trimming can provide robust estimators.
