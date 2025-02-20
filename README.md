# Asymptotic Relative Efficiency (ARE) of Sample Mean vs. Trimmed Mean

## Problem Description

Given i.i.d. random variables:

$$ X_1, X_2, ..., X_n \sim N(\mu, \sigma^2) $$

we compare two estimators for $\mu$:  

1. **Sample Mean**:
   $$ \bar{X} = \frac{1}{n} \sum_{i=1}^{n} X_i $$  

2. **Trimmed Mean** (removing smallest and largest $\alpha n$ values):
   $$ \bar{X}_\alpha = \frac{1}{n - 2k} \sum_{i=k+1}^{n-k} X_{(i)} $$  
   where $k = \lfloor \alpha n \rfloor$.

## Asymptotic Relative Efficiency (ARE)

Defined as:

$$ ARE(\bar{X}, \bar{X}_\alpha) = \frac{\text{Var}(\bar{X})}{\text{Var}(\bar{X}_\alpha)} $$

The variance of $\bar{X}_\alpha$ is:

$$ \text{Var}(\bar{X}_\alpha) = \frac{\sigma^2}{(1 - 2\alpha)^2 n} \left(1 - \frac{z_{1-\alpha} \varphi(z_{1-\alpha}) - z_\alpha \varphi(z_\alpha)}{\Phi(z_{1-\alpha}) - \Phi(z_\alpha)} \right) $$  

where:
- $\varphi(z)$ = standard normal PDF  
- $\Phi(z)$ = standard normal CDF  
- $z_\alpha = \Phi^{-1}(\alpha)$, $z_{1-\alpha} = \Phi^{-1}(1 - \alpha)$  

Final ARE formula:

$$ ARE(\bar{X}, \bar{X}_\alpha) = \frac{(1 - 2\alpha)^2}{1 - \frac{z_{1-\alpha} \varphi(z_{1-\alpha}) - z_\alpha \varphi(z_\alpha)}{\Phi(z_{1-\alpha}) - \Phi(z_\alpha)}} $$  

## Monte Carlo Simulation

We validate the ARE formula by simulating $X_i \sim N(2,4)$ and comparing empirical variances of $\bar{X}$ and $\bar{X}_\alpha$.

## Conclusion

Theoretical and empirical results confirm the efficiency loss of the trimmed mean compared to the standard mean, useful for robust estimation.

