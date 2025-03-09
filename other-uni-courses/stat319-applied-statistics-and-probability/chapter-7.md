# Chapter 7: Sampling Distributions

## Table of Contents

- [Chapter 7: Sampling Distributions](#chapter-7-sampling-distributions)
  - [Table of Contents](#table-of-contents)
  - [Objectives](#objectives)
  - [7.1 Introduction](#71-introduction)
  - [7.2 Sampling distribution and the Sampling error](#72-sampling-distribution-and-the-sampling-error)
    - [Sampling Error](#sampling-error)
    - [Developing a sampling distribution](#developing-a-sampling-distribution)
    - [Central Limit Theorem](#central-limit-theorem)

## Objectives

- The concept of the sampling distribution
  - Determine mean and standard deviation for the sampling distribution of the sample mean, $\bar{x}$
- Describe the Central Limit Theorem and its importance
- To compute probabilities related to the sample mean and the sample proportion

## 7.1 Introduction

Recall in chapter 3 we talked about discrete probability distributions, including Binomial, Hypergeometric, and Poisson.

In chapter 4, we delved into the world of continuous distributions and discussed continuous distributions like Normal, Exponential, Weibull, and Lognormal.

We always assumed we know the parameter of the distribution. For example, we know the mean and variance for the Normal distributed random variable.

However, this is NOT usually the case. In the case where we don't know, what should we do?
Simply, we use **statistical inference**, which deals with making probabilistic statements about a
population of individuals based on info that is contained in a sample taken from the population.

## 7.2 Sampling distribution and the Sampling error

The following info have been discussed before and are very logical but let us restate them.

1. The sample mean $\bar{x}$ is an estimator of the population mean $\mu$.
2. The sample standard deviation $s =\sqrt{\frac{\sum x^2 - n \bar{x}^2}{n-1}}$ is an estimator of the population $\sigma$.
3. The sample proportion $\hat{p} = \frac{x}{n}$ is an estimator of the population $P$.

Simply, **the sample statistics are estimators of the population parameters**.

Since different samples provide different estimates, the sampling error exists.

### Sampling Error

The difference between a statistic and a parameter is the *sampling error*.

$Sampling \ error = \bar{x} - \mu$

It is very clear that:

1. different samples have different errors
2. the error may be positive (overestimate) or negative (underestimate)
3. The expected sampling error as the sample size increases.

Our goal is to find the mean (expected value) and the variance of the sample statistic.

### Developing a sampling distribution

A **sampling distribution** is a distribution of the possible values of a statistic for a given size sample selected from a population.

Note the following steps to create a sampling distribution that estimates the population mean:

1. Select all possible samples of a certain size WITH REPLACEMENT.
2. Build a frequency table of sample means (means of all the samples).
3. Find the mean $\mu_{\bar{x}}$ and variance $\sigma^{2}_{\bar{x}}$ of sample means

If we assume our population to be normally distributed, then the means and standard deviations above will be:

$\mu_{\bar{x}} = \mu$
$\sigma_{\bar{x}} = \frac{\sigma}{\sqrt{n}}$ Known as the standard error

The Z score is also straightforward:

$Z = \frac{\bar{x} - \mu_{\bar{x}}}{\sigma_{\bar{x}}} = \frac{(\bar{x} - \mu) \sqrt{n}}{\sigma}$

### Central Limit Theorem

Given a normally distributed population and a fairly large sample size ($\ge 30$), the sampling distribution of the sample mean will be approximately normal with the above mean and standard deviation.

For fairly symmetric distributions, $\ge 5$ is even enough.