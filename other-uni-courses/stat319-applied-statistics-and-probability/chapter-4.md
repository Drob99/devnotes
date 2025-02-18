# Chapter 4: Continuous Random Variables & Probability Distributions

## Table of Contents

- [Chapter 4: Continuous Random Variables \& Probability Distributions](#chapter-4-continuous-random-variables--probability-distributions)
  - [Table of Contents](#table-of-contents)
  - [Objectives](#objectives)
  - [4.1 - 4.4: Continuous Random Variable](#41---44-continuous-random-variable)

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

