# Problem 1
# 1. Setup and Preparation

## Objective

The objective of this study is to **empirically validate** the Central Limit Theorem (CLT) through simulation. The CLT asserts that, given a sufficiently large sample size $n$, the distribution of the sample mean $\bar{X}$ will approximate a normal distribution, regardless of the shape of the population distribution, provided the population has finite mean $\mu$ and finite variance $\sigma^2$.

Formally:

$$
\bar{X}_n = \frac{1}{n} \sum_{i=1}^n X_i \xrightarrow{d} \mathcal{N}\left(\mu, \frac{\sigma^2}{n}\right) \quad \text{as} \quad n \to \infty
$$

where:

- $X_i$ are i.i.d. random variables with mean $\mu$ and variance $\sigma^2$
- $\bar{X}_n$ is the sample mean
- $\xrightarrow{d}$ denotes convergence in distribution

The study aims to demonstrate this convergence by simulating various population distributions and observing the behavior of the sample mean.

---

## Scope of Simulation

This study will involve:

1. Constructing large synthetic populations from known distributions:
    - Uniform
    - Exponential
    - Binomial

2. Drawing multiple random samples of various sizes (e.g., $n = 5, 10, 30, 50$)

3. Computing the sample means:
   $$
   \bar{X}_n = \frac{1}{n} \sum_{i=1}^n X_i
   $$

4. Analyzing the distribution of these sample means across different sample sizes and original distributions.

---

## Programming Environment

To conduct this simulation study, we will use **Python** due to its extensive support for scientific computing and data visualization. The following libraries will be essential:

- `NumPy`: For random sampling and numerical operations
- `Matplotlib`: For basic plotting
- `Seaborn`: For enhanced statistical visualizations

### Required Python Libraries

```python
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
# 2. Population Distribution Generation

## Purpose

To explore the Central Limit Theorem (CLT), we first need to generate **synthetic populations** that serve as the origin of samples. These populations will be drawn from three statistically distinct distributions:

- **Uniform Distribution**
- **Exponential Distribution**
- **Binomial Distribution**

Each of these will highlight different characteristics (e.g., skewness, discreteness) that allow us to study the robustness of the CLT.

---

## 2.1 Uniform Distribution

### Definition

A continuous distribution with constant probability over an interval $[a, b]$:

$$
X \sim \text{Uniform}(a, b)
$$

### Probability Density Function (PDF)

$$
f(x) = 
\begin{cases}
\frac{1}{b - a} & \text{for } x \in [a, b] \\
0 & \text{otherwise}
\end{cases}
$$

### Statistical Properties

- Mean: $\mathbb{E}[X] = \frac{a + b}{2}$
- Variance: $\text{Var}(X) = \frac{(b - a)^2}{12}$

### Example Parameters

- $a = 0$, $b = 10$
- Hence, $\mu = 5$, $\sigma^2 = \frac{100}{12} \approx 8.33$

---

## 2.2 Exponential Distribution

### Definition

A continuous distribution often used to model time until an event (e.g., failure time, interarrival time):

$$
X \sim \text{Exponential}(\lambda)
$$

### Probability Density Function (PDF)

$$
f(x) = 
\begin{cases}
\lambda e^{-\lambda x} & \text{for } x \geq 0 \\
0 & \text{otherwise}
\end{cases}
$$

### Statistical Properties

- Mean: $\mathbb{E}[X] = \frac{1}{\lambda}$
- Variance: $\text{Var}(X) = \frac{1}{\lambda^2}$

### Example Parameters

- $\lambda = 1$
- Hence, $\mu = 1$, $\sigma^2 = 1$

*Note: The exponential distribution is positively skewed and will be useful to demonstrate the CLT’s effectiveness on skewed data.*

---

## 2.3 Binomial Distribution

### Definition

A discrete distribution representing the number of successes in $n$ independent Bernoulli trials with success probability $p$:

$$
X \sim \text{Binomial}(n, p)
$$

### Probability Mass Function (PMF)

$$
P(X = k) = \binom{n}{k} p^k (1 - p)^{n - k} \quad \text{for } k = 0, 1, \dots, n
$$

### Statistical Properties

- Mean: $\mathbb{E}[X] = np$
- Variance: $\text{Var}(X) = np(1 - p)$

### Example Parameters

- $n = 10$, $p = 0.5$
- Hence, $\mu = 5$, $\sigma^2 = 2.5$

---

## Data Generation Strategy

For each distribution:

1. **Set known parameters** $\theta$ (e.g., $a, b$ or $\lambda$ or $n, p$)
2. **Generate large population** of size $N = 100,000$
3. **Store for sampling**

### Python Code Snippet

```python
N = 100000  # Population size

# Uniform distribution
uniform_pop = np.random.uniform(0, 10, size=N)

# Exponential distribution
exponential_pop = np.random.exponential(scale=1.0, size=N)  # scale = 1/lambda

# Binomial distribution
binomial_pop = np.random.binomial(n=10, p=0.5, size=N)
# 3. Sampling Process

## Purpose

The goal of this stage is to simulate the **sampling distribution of the sample mean** for various sample sizes and population distributions. This process enables us to observe the **convergence toward normality**, as predicted by the Central Limit Theorem (CLT).

---

## Sample Sizes

We choose a range of sample sizes that are commonly used in statistical analysis to explore how quickly the CLT begins to take effect. Specifically, we use:

$$
n \in \{5, 10, 30, 50\}
$$

These values allow us to assess the evolution of the sampling distribution shape from small to moderately large sample sizes.

---

## Procedure Overview

For each **population distribution** $D$ and each **sample size** $n$, we will:

1. Draw $M$ independent random samples of size $n$:
   $$
   \{X_{i1}, X_{i2}, \ldots, X_{in}\}, \quad \text{for } i = 1, 2, \ldots, M
   $$
2. Compute the sample mean for each sample:
   $$
   \bar{X}_i = \frac{1}{n} \sum_{j=1}^n X_{ij}
   $$
3. Store all $\bar{X}_i$ to form the empirical **sampling distribution** of the mean:
   $$
   \left\{\bar{X}_1, \bar{X}_2, \ldots, \bar{X}_M \right\}
   $$

### Parameters Used

- $M = 1000$ samples per condition (distribution × sample size)
- $n = 5$, $10$, $30$, $50$
- Distributions: Uniform, Exponential, Binomial (as defined earlier)

---

## Python Code Snippet (Conceptual)

```python
M = 1000  # Number of samples per condition
sample_sizes = [5, 10, 30, 50]

sampling_means = {
    "Uniform": {},
    "Exponential": {},
    "Binomial": {}
}

for dist_name, population in {
    "Uniform": uniform_pop,
    "Exponential": exponential_pop,
    "Binomial": binomial_pop
}.items():
    for n in sample_sizes:
        means = [
            np.mean(np.random.choice(population, size=n, replace=False))
            for _ in range(M)
        ]
        sampling_means[dist_name][n] = means


