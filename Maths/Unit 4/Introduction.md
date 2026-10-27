[Maths Index](../README.md)

# Unit 4: Hypothesis Testing and Statistical Inference

Welcome to Unit 4 of **Mathematical Foundation for AI & Data Science (Statistical Inference)**.

In Unit 3, we explored how to estimate unknown parameters and place confidence intervals around them. But in scientific discovery, data analysis, and A/B testing for artificial intelligence systems, estimation is only half the battle. Often, we must make a definitive decision: *Does this new algorithm perform significantly better than the baseline, or is the observed improvement merely random noise?*

Unit 4 covers the formal decision-making framework of inferential statistics:
- **Foundations of Hypothesis Testing**: Null hypothesis ($H_0$), Alternative hypothesis ($H_1$), test statistics, rejection regions, and significance levels ($\alpha$).
- **Large-Sample Hypothesis Tests**: One-sample and two-sample $Z$-tests for population means and proportions.
- **Decision Rules & Interpretation**: Critical value approach vs. $p$-value approach, and drawing valid statistical conclusions.
- The deep mathematical relationship and **duality between Confidence Intervals and Two-Sided Hypothesis Tests**.
- **Small-Sample Hypothesis Tests**: Student's $t$-test when population standard deviation $\sigma$ is unknown.
- Decision errors and validation: **Type I Error ($\alpha$)**, **Type II Error ($\beta$)**, and the **Power of a Test ($1 - \beta$)**.
- Testing differences across multiple categories simultaneously: **Analysis of Variance (One-Way ANOVA)** and the $F$-distribution.
- Non-parametric testing for categorical data: **Chi-Square ($\chi^2$) Goodness-of-Fit Test** and **Chi-Square Tests of Independence and Homogeneity**.

---

## Unit 4 Roadmap

- [**L01 - Foundations of Hypothesis Testing**](L01%20-%20Foundations%20of%20Hypothesis%20Testing.md) — The scientific logic of statistical falsification, formulating Null ($H_0$) and Alternative ($H_1$) hypotheses, one-tailed vs. two-tailed tests, test statistics, and significance level $\alpha$.
- [**L02 - Large-Sample Tests for a Population Mean**](L02%20-%20Large-Sample%20Tests%20for%20a%20Population%20Mean.md) — Large sample $Z$-test for a single mean, critical values ($z_\alpha, z_{\alpha/2}$), calculating and interpreting $p$-values, and making rigorous accept/reject decisions.
- [**L03 - Confidence Intervals and Hypothesis Testing Relationship**](L03%20-%20Confidence%20Intervals%20and%20Hypothesis%20Testing%20Relationship.md) — Duality between $(1-\alpha)$ confidence intervals and two-sided $\alpha$-level tests, equivalence proofs, and statistical vs. practical significance.
- [**L04 - Small-Sample Tests for a Population Mean**](L04%20-%20Small-Sample%20Tests%20for%20a%20Population%20Mean.md) — The one-sample $t$-test with unknown variance, degrees of freedom, robustness against non-normality, and two-sample pooled/unpooled $t$-tests.
- [**L05 - Type I and Type II Errors**](L05%20-%20Type%20I%20and%20Type%20II%20Errors.md) — The error matrix, false positives (Type I error $\alpha$), false negatives (Type II error $\beta$), trade-offs between $\alpha$ and $\beta$, and the consequences of sample size on error rates.
- [**L06 - Power of a Test and Factors Affecting Power**](L06%20-%20Power%20of%20a%20Test%20and%20Factors%20Affecting%20Power.md) — Statistical power ($1 - \beta$), power curves, effect size (Cohen's $d$), sample size determination for desired power, and trade-offs in experimental design.
- [**L07 - Analysis of Variance - One-Way ANOVA**](L07%20-%20Analysis%20of%20Variance%20-%20One-Way%20ANOVA.md) — Multiple group comparisons, inflation of family-wise Type I error rate, Sum of Squares (Total, Between, Within), mean squares, and the $F$-test statistic.
- [**L08 - Chi-Square Goodness-of-Fit Test**](L08%20-%20Chi-Square%20Goodness-of-Fit%20Test.md) — Testing categorical distributions against theoretical expectations, observed vs. expected frequencies, degrees of freedom, and the $\chi^2$ test statistic.
- [**L09 - Chi-Square Tests of Independence and Homogeneity**](L09%20-%20Chi-Square%20Tests%20of%20Independence%20and%20Homogeneity.md) — Contingency tables ($r \times c$), calculating expected cell counts, testing independence between two categorical variables, and testing homogeneity across distinct populations.

---

## Objectives

- Formulate null and alternative hypotheses for real-world research and engineering questions.
- Conduct large-sample $Z$-tests and small-sample $t$-tests, computing test statistics and $p$-values.
- Explain and exploit the duality between confidence intervals and hypothesis tests.
- Identify, quantify, and minimize Type I and Type II errors in testing frameworks.
- Calculate and analyze the statistical power of tests and determine required sample sizes.
- Perform One-Way ANOVA to test equality of multiple group means without Type I error inflation.
- Implement Chi-Square tests to verify distribution goodness-of-fit and independence in contingency tables.

---

Let's begin by mastering the foundational logic of hypothesis testing and statistical falsification. Read [**L01 - Foundations of Hypothesis Testing**](L01%20-%20Foundations%20of%20Hypothesis%20Testing.md).
