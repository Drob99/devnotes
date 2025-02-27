# Chapter 4: Continuous Random Variables & Probability Distributions

## Table of Contents

- [Chapter 4: Continuous Random Variables \& Probability Distributions](#chapter-4-continuous-random-variables--probability-distributions)
  - [Table of Contents](#table-of-contents)
  - [Objectives](#objectives)
  - [4.1 - 4.4: Continuous Random Variable](#41---44-continuous-random-variable)
  - [4.6: Normal Distribution](#46-normal-distribution)
    - [Empirical rule](#empirical-rule)
    - [The Standard Normal Distribution](#the-standard-normal-distribution)
    - [The Critical Value](#the-critical-value)
  - [4.8: The Exponential Distribution](#48-the-exponential-distribution)
  - [4.10: Weibull Distribution](#410-weibull-distribution)
  - [4.11: Lognormal Distribution](#411-lognormal-distribution)

## Objectives

- Determine probabilities from the PDF (probability density function) & the CDF (cumulative distribution functions).
- Calculate the mean and the variance for continuous random variables.
- Understand the assumptions, calculate the probabilities, determine means and variances for some common continuous probability distributions.
- Standardize normal random variable.

---

## 4.1 - 4.4: Continuous Random Variable

It has only continuous values (an uncountable number of possible values).
Examples:
    - thickness of an item
    - time required to complete a task
    - height in cm
    - temperature of a solution

The function associated with the continuous probability is known as **Probability Density Function (PDF)**.

Conditions:
    1. Must be completely above x-axis: $f(x) \ge 0$
    2. Total area under the curve must equal $\int^{ \infin }_{-\infin} f(x) dx = 1$

The PDF gives the probability of a random variable.
The **cumulative distribution function (CDF)** for the random variable is given by

$$
F(x) = P(X \le x) = \int^{x}_{-\infin} f(u) du, -\infin < x < +\infin
$$

Consider the following example. Assume $a$ and $b$ are points on a PDF curve.
Let $X$ be a continuous random variable, then

1. The probability of $X$ between $a$ & $b$ is equal to area under the curve

$$
P(a \le b) = \int_{a}^{b} f(x) dx = F(b) - F(a)
$$

2. $P(X=c) = 0$ The probability of a single number is always ZERO.
3. Expected value $\mu_x = E(X) = \int_{-\infin}^{\infin} x f(x) dx$
4. Variance $\sigma_x^2 = E(X^2) - E(X)^2 = E(x^2) - \mu^2 = \int_{-\infin}^{\infin} x^2 f(x) dx - ( \int_{-\infin}^{\infin} x f(x) dx)^2$
5. $P(a < X < b) = P(a \le X \le b) = P(a < X \le b) = P(a \le X < b) = \int_{a}^{b} f(x) dx$
6. The median is the value such that the area under the curve to the left is 50% $P(X < a) = 0.5 = \int_{-\infin}^{a} f(x) dx$

## 4.6: Normal Distribution

A bell-shaped curve with the following properties:

1. unimodal (peaks at a single value)
2. symmetrical around the mean (mean = median = mode)
3. Random variable has an infinite range
4. Location is determined by the mean
5. Spread is determined by standard deviation

$f(x) = \frac{1}{2\pi\sigma^2} e^{-\frac{1}{2}(\frac{x-\mu}{\sigma})^2}, -\infin \le x \le +\infin$

### Empirical rule

About 68% of the values are around 1 standard deviation of the mean.
About 95% of the values are around 2 standard deviations of the mean.
About 99.7% of the values are around 3 standard deviations of the mean.

### The Standard Normal Distribution

If a normal distribution has a mean ($\mu$) and a standard deviation ($\sigma$) and $Z = \frac{x-\mu}{\sigma}$, then $Z$ has a standard normal distribution with a mean of 0 and standard deviation of 1.

$\mu_{Z} = E(Z) = E(\frac{x-\mu}{\sigma}) = \frac{1}{\sigma} (E(x) - E(\mu)) = \frac{1}{\sigma} (\mu - \mu) = 0$

$\sigma^2_Z = Var(Z) = Var(\frac{x-\mu}{\sigma}) = \frac{1}{\sigma^2} (Var(x) + Var(\mu)) = \frac{1}{\sigma^2} (\sigma^2) = 1$

The Z-table helps you find cumulative probabilities about the Z, or standard normal distribution.

### The Critical Value

A value ($a$) given to the area to the right under the standard normal distribution equal to $\alpha$ and denoted by $Z_\alpha$

$Z_\alpha = a$, such that $P(Z > a) = \alpha$

## 4.8: The Exponential Distribution

Used to model the time btw two occurrences of an event

PDF: $f(x) = \lambda e^{\lambda x}, x \ge 0$, where lambda is mean number of events per unit interval

Mean: $E(X) = \mu = \frac{1}{\lambda}$
Variance: $\sigma^2_x = \frac{1}{\lambda^2}$

For any exponential distribution, $f(0) = \lambda$, and as x increases, f(x) approaches 0.

CDF: $F(a) = P(X \le a) = \int_{0}^{a} \lambda e^{-\lambda x} dx = 1 - e^{\lambda a}$

## 4.10: Weibull Distribution

Often used to model time until failure of many different systems.

PDF: $f(x) = \frac{\beta}{\delta} (\frac{x}{\delta})^{\beta-1} e^{-(\frac{x}{\delta})^{\beta}}, x > 0$

delta is scale factor
beta is shape parameter

When shape parameter is 1, then this the Weibull is identical to exponential.

CDF: $F(x) = P(X < x) = 1 - e^{-(\frac{x}{\delta})^\beta}$

Mean: $\mu = \delta \Gamma (1 + \frac{1}{\beta})$

Variance: $\sigma^2 = E(X^2) - E(X)^2 = \delta^2 \Gamma (1 + \frac{2}{\beta}) - \delta^2 (\Gamma (1 + \frac{1}{\beta}))^2$

Definition:

1. $\Gamma (r) = \int_{0}^{r} x^{r-1} e^{-x} dx, r > 0$
2. If r integer, then $\Gamma(r) = (r-1)!$
3. For any r, $\Gamma(r+1) = r\Gamma(r)$
4. $\Gamma(\frac{1}{2}) = sqrt(\pi)$
5. $\Gamma(1) = 0! = 1$

## 4.11: Lognormal Distribution

When the data contain outliers, the normal distribution might be not appropriate.

Let $W$ denote a random variable with
  mean: $\theta$ (scale parameter)
  variance: $\omega^2$ (shape parameter)

then $X = e^W$ is a lognormal random variable with

PDF: $f(x) = \frac{1}{x \omega sqrt(2\pi)} e^{-\frac{(\ln x-\theta)^2}{2 \omega^2}}$

Mean: $\mu = e^{\theta + \frac{\omega^2}{2}}$
Variance: $\sigma^2 = e^{2\theta + \omega^2} (e^{\omega^2} - 1)$

Note that $\ln X = W$ where the natural log of X is normally distributed.
Range of X is (0, $\infin$)

CDF:
$F(x) = P(X \le x) \\ = P(e^{W} \le x) \\ = P(W \le \ln x) \\ = P(\frac{W-\theta}{\omega} \le \frac{\ln x - \theta}{\omega}) \\ = P(Z \le \frac{\ln x - \theta}{\omega})$, for x > 0, where Z is standard normal variable

$F(x) = 0$ for $x \le 0$

