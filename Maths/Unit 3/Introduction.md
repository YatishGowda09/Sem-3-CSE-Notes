[Maths Index](../README.md)

# Unit 3: Probability Modeling and Parameter Estimation

Welcome to Unit 3 of **Mathematical Foundation for AI & Data Science (Probability & Statistics)**.

Where Units 1 and 2 established deterministic linear mappings, vector spaces, and projections, real-world data is inherently noisy, incomplete, and stochastic. Unit 3 introduces the mathematical machinery required to quantify uncertainty, model probabilistic processes, and estimate parameters from empirical observations.

Unit 3 explores the foundational theory of statistical modeling and estimation:
- How real-world systems are modeled through **Probability and Sampling Frameworks**.
- How outcomes are quantified using **Random Variables**, Probability Mass Functions (PMF), Probability Density Functions (PDF), and Cumulative Distribution Functions (CDF).
- The fundamental continuous and discrete distributions: **Bernoulli, Binomial, Poisson, Uniform, and the Gaussian (Normal) Distribution**.
- Joint distributions, covariance, correlation, and **Multivariate Probability Distributions**.
- The mathematical bedrock of inferential statistics: **The Central Limit Theorem (CLT)**.
- **Principles of Point Estimation**: sample statistics, bias, variance, and Mean Squared Error (MSE).
- The optimization engine of machine learning: **Maximum Likelihood Estimation (MLE)**.
- Bayesian estimation: **Maximum A Posteriori (MAP)** and the **Multivariate Normal Distribution**.
- Quantifying parameter uncertainty: **Interval Estimation**, large-sample Confidence Intervals, the **Student's t-Distribution**, and factors affecting the Margin of Error.

---

## Unit 3 Roadmap

- [**L01 - Introduction to Probability Modeling and Sampling**](L01%20-%20Introduction%20to%20Probability%20Modeling%20and%20Sampling.md) — Population vs. sample, sample spaces, probability axioms, sampling techniques (simple random, stratified, cluster, systematic), and sampling bias.
- [**L02 - Random Variables and Probability Distributions**](L02%20-%20Random%20Variables%20and%20Probability%20Distributions.md) — Discrete vs. continuous random variables, PMF, PDF, CDF properties, expectation (mean), variance, and standard deviation.
- [**L03 - Common Probability Distributions**](L03%20-%20Common%20Probability%20Distributions.md) — Bernoulli trials, Binomial distribution, Poisson process, Uniform distribution, and the Gaussian / Normal distribution ($Z$-score standardization).
- [**L04 - Multivariate Distributions and Independence**](L04%20-%20Multivariate%20Distributions%20and%20Independence.md) — Joint PMF/PDF, marginal distributions, conditional distributions, statistical independence, covariance, and Pearson correlation coefficient.
- [**L05 - The Central Limit Theorem**](L05%20-%20The%20Central%20Limit%20Theorem.md) — Sampling distribution of the sample mean, standard error of the mean, the Central Limit Theorem statement, convergence mechanics, and sample size guidelines ($n \ge 30$).
- [**L06 - Principles of Point Estimation**](L06%20-%20Principles%20of%20Point%20Estimation.md) — Estimators vs. estimates, unbiasedness, efficiency, consistency, Mean Squared Error (MSE), and the Bias-Variance tradeoff.
- [**L07 - Maximum Likelihood Estimation**](L07%20-%20Maximum%20Likelihood%20Estimation.md) — Likelihood function $L(\theta)$, log-likelihood $\ln L(\theta)$, score function, solving score equations for Bernoulli and Normal parameters ($\mu$ and $\sigma^2$).
- [**L08 - Maximum A Posteriori and Multivariate Normal**](L08%20-%20Maximum%20A%20Posteriori%20and%20Multivariate%20Normal.md) — Bayes' theorem in parameter estimation, prior distributions, posterior distributions, MAP estimation, and the geometry of the Multivariate Normal distribution.
- [**L09 - Interval Estimation and Confidence Intervals**](L09%20-%20Interval%20Estimation%20and%20Confidence%20Intervals.md) — Point estimate limitations, confidence levels ($1 - \alpha$), critical values $z_{\alpha/2}$, large-sample confidence intervals for population mean, and sample size determination.
- [**L10 - Student's t-Distribution and Small Sample Intervals**](L10%20-%20Student's%20t-Distribution%20and%20Small%20Sample%20Intervals.md) — Unknown population variance, degrees of freedom, heavy-tailed properties of Student's t-distribution, small-sample confidence intervals, and factors affecting the Margin of Error.

---

## Objectives

- Differentiate between populations, samples, and probabilistic sampling mechanisms.
- Calculate expectations, variances, and probabilities across standard discrete and continuous distributions.
- Apply the Central Limit Theorem to predict sampling distributions of the sample mean.
- Evaluate estimator quality using bias, variance, and Mean Squared Error.
- Derive Maximum Likelihood Estimators (MLE) for standard parametric distributions.
- Compare Frequentist MLE with Bayesian Maximum A Posteriori (MAP) estimation.
- Construct and interpret large-sample and small-sample confidence intervals for population parameters.
- Analyze how confidence level, sample size, and variance impact the Margin of Error.

---

Let's begin by establishing how empirical data is collected and modeled probabilistically. Read [**L01 - Introduction to Probability Modeling and Sampling**](L01%20-%20Introduction%20to%20Probability%20Modeling%20and%20Sampling.md).
