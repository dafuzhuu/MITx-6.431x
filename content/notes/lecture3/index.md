+++
title = 'Lecture 3: Parametric Statistical Models'
date = 2024-09-17T19:48:14+08:00
draft = false
+++

{{< bilibili BV1af4y1K7TE >}}

## Statistical Model for a Censored Exponential

1 point possible (graded)

Let `$ X $` denote an exponential random variable with unknown parameter `$ \lambda > 0 $`. Let `$ Y = \mathbb{I}(X > 5) $`, the indicator that `$ X $` is larger than 5.

Recall the definition of the indicator function here is:

`$$
\mathbb{I}(X > 5) = 
\begin{cases} 
1 & \text{if } X > 5 \\
0 & \text{if } X \leq 5.
\end{cases}
$$`

We think of `$ Y $` as a censored version of the Exponential random variable `$ X $`: we cannot directly observe `$ X $`, but we are able to gather some information about it (in this case, whether or not `$ X $` is larger than 5).

Observe that `$ Y $` is a Bernoulli random variable. Thus, the statistical model for `$ Y $` can be written `$ (\{0, 1\}, \{\text{Ber} (f(\lambda))\}_{\lambda > 0}) $` for some function `$ f(\lambda) $`. What is `$ f(\lambda) $`?

(Type lambda for `$ \lambda $`. Use the help button below for help with formula input).

`$$
f(\lambda) = 
$$`

**Solution:**

Note that `$ Y = 1 $` if and only if `$ X > 5 $`. Hence, we need to compute the probability that `$ X > 5 $`. Recall that the density of `$ \text{Exp}(\lambda) $` is given by `$ \lambda e^{-\lambda x} $`. We just need to compute:

`$$
P(X > 5) = \int_{5}^{\infty} \lambda e^{-\lambda x} \, dx = e^{-5\lambda}.
$$`

We conclude that if `$ X \sim \text{Exp}(\lambda) $`, then `$ Y \sim \text{Ber}(e^{-5\lambda}) $`. Hence, `$ f(\lambda) = e^{-5\lambda} $`.



## Mean and Variance of a Mixture

3 points possible (graded)

Recall that `$ X $` follows a mixture of two Gaussians if and only if

`$$
X = Z X_1 + (1 - Z) X_2
$$`

where `$ Z \sim \text{Ber}(\pi) $`, `$ X_1 \sim \mathcal{N}(\mu_1, \sigma_1^2) $`, `$ X_2 \sim \mathcal{N}(\mu_2, \sigma_2^2) $` and `$ Z $` is independent of `$ X_1 $` and `$ X_2 $`.

Assume that `$ \mu_1 = 0 $`, `$ \mu_2 = 1 $` and `$ \sigma_1^2 = \sigma_2^2 = 1 $` and `$ \pi = 1/4 $`.

*Note that `$\pi$` here is not the constant 3.14...*

**What is the expected value of `$ X $`?**

`$$
\mathbb{E}[X] = \frac{3}{4}
$$`

**What is the variance of `$ X $`?**

`$$
\text{Var}(X) = 
$$`

**For the above computations, do you have to assume that `$ X_1 $` is independent of `$ X_2 $`?**

- [ ] Yes  
- [ ] No  

**Solution:**

In this explanation, the goal is to find the variance of `$ X $` where `$ X $` follows a mixture of two Gaussians. The mixture is defined by:

`$$
X = ZX_1 + (1 - Z)X_2,
$$`

where:
- `$ Z \sim \text{Ber}(\pi) $` with `$\pi = \frac{1}{4}$`,
- `$ X_1 \sim \mathcal{N}(0, 1) $`,
- `$ X_2 \sim \mathcal{N}(1, 1) $`.

The provided solution uses the probability density functions (pdfs) of the Gaussian distributions to compute the second moment `$\mathbb{E}[X^2]$`.

1. **Density of the Mixture**:
   The mixture density of `$ X $` is given by:

   `$$
   (1/4) \phi_{0,1}(x) + (3/4) \phi_{1,1}(x),
   $$`

   where `$\phi_{\mu, \sigma^2}(x)$` represents the pdf of a Gaussian distribution with mean `$\mu$` and variance `$\sigma^2$`. Specifically, `$\phi_{0,1}(x)$` corresponds to a Gaussian with mean 0 and variance 1, and `$\phi_{1,1}(x)$` corresponds to a Gaussian with mean 1 and variance 1.

2. **Computing the Second Moment `$\mathbb{E}[X^2]$`**:
   To find the variance of `$X$`, you first need the second moment, `$\mathbb{E}[X^2]$`. The second moment is computed by integrating `$x^2$` against the mixture density:

   `$$
   \mathbb{E}[X^2] = \int x^2 \left( (1/4) \phi_{0,1}(x) + (3/4) \phi_{1,1}(x) \right) dx.
   $$`

   By linearity of expectation:

   `$$
   \mathbb{E}[X^2] = (1/4) \mathbb{E}[X_1^2] + (3/4) \mathbb{E}[X_2^2].
   $$`

3. **Calculating `$\mathbb{E}[X_1^2]$` and `$\mathbb{E}[X_2^2]$`**:
   - For `$X_1 \sim \mathcal{N}(0, 1)$`, `$\mathbb{E}[X_1^2] = \text{Var}(X_1) + (\mathbb{E}[X_1])^2 = 1 + 0 = 1$`.
   - For `$X_2 \sim \mathcal{N}(1, 1)$`, `$\mathbb{E}[X_2^2] = \text{Var}(X_2) + (\mathbb{E}[X_2])^2 = 1 + 1 = 2$`.

   Plug these into the expression for `$\mathbb{E}[X^2]$`:

   `$$
   \mathbb{E}[X^2] = (1/4) \cdot 1 + (3/4) \cdot 2 = \frac{1}{4} + \frac{6}{4} = \frac{7}{4}.
   $$`

4. **Finding the Variance of `$X$`**:
   The variance of `$X$` is:

   `$$
   \text{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2.
   $$`

   You already know that `$\mathbb{E}[X] = \frac{3}{4}$`, so:

   `$$
   \text{Var}(X) = \frac{7}{4} - \left(\frac{3}{4}\right)^2 = \frac{7}{4} - \frac{9}{16}.
   $$`

   Simplifying:

   `$$
   \text{Var}(X) = \frac{28}{16} - \frac{9}{16} = \frac{19}{16}.
   $$`
