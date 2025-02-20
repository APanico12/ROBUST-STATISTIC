# Asymptotic Relative Efficiency (ARE) of the Sample Mean vs. Trimmed Mean

## Problem Description

We consider a set of independent and identically distributed (iid) random variables:

$$ X_1, X_2, \ldots, X_n \sim N(\mu, \sigma^2) $$

where $ N(\mu, \sigma^2) $ denotes a normal distribution with mean $ \mu $ and variance $ \sigma^2 $. Our goal is to compare the efficiency of two estimators for $ \mu $:

1. **Sample Mean** $ \bar{X} $:
   $$ \bar{X} = \frac{1}{n} \sum_{i=1}^{n} X_i $$

2. **Trimmed Mean** $ \bar{X}_\alpha $ with a symmetric trimming proportion $ \alpha $, which removes the smallest and largest $ \alpha n $ values:
   $$ \bar{X}_\alpha = \frac{1}{n - 2k} \sum_{i=k+1}^{n-k} X_{(i)} $$

   where $ k = \lfloor \alpha n \rfloor $ and $ X_{(i)} $ are the order statistics.

The efficiency of these estimators is measured through the **Asymptotic Relative Efficiency (ARE)**, defined as the ratio of their asymptotic variances:

$$ \text{ARE}(\bar{X}, \bar{X}_\alpha) = \frac{\operatorname{Var}(\bar{X})}{\operatorname{Var}(\bar{X}_\alpha)} $$

## Analytical Result

Using standard results for truncated normal moments, the variance of the trimmed mean is given by:

$$ \operatorname{Var}(\bar{X}_\alpha) = \frac{\sigma^2}{(1 - 2\alpha)^2 n} \left( 1 - \frac{z_{1-\alpha} \varphi(z_{1-\alpha}) - z_\alpha \

