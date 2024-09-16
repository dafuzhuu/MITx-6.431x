+++
title = 'Lecture 2: Probability Redux'
date = 2024-09-17T00:24:28+08:00
draft = false
math = true
+++

## Two important probability tools

{{< youtube 0XDbzLlu5r4 >}}

### SAT

Up until 2015, the SAT had a "guessing penalty". Consider an exam with 40 questions each with six possible choices. Only one is correct. Each correct answer is worth +20 points and each incorrect one is worth -5 points. Consider answering each question by rolling a six-sided die for each question and simply choosing the corresponding answer.

1. What is your expected score for the first question?

[Hint: First write your score for this question as $aX+b$ where `$X \sim \text {Ber}(p)$` for some numbers `$a,b$` and $p$ to be determined.]

2. What is the standard deviation of your total score on the exam?

3. What is the probability that you score more than 400 points? Use the CLT.

4. What is the probability that you score more than 600 points? Use the CLT.

![SAT](img/SAT.png)


### Formulations of CLT

Suppose that $ X_1, \ldots, X_n $ are i.i.d. with mean $\mu$ and variance $\sigma^2$. Which of the following are equivalent statements of the central limit theorem seen in class? (Choose all that apply.)

**Options:**

1. `$\frac{\bar{X}_n - \mu}{\sigma} \to N \left( 0, \frac{\sigma^2}{n} \right)$`

2. `$\sqrt{n} \left( \frac{\bar{X}_n - \mu}{\sigma} \right) \to N(0, 1)$`

3. `$\frac{1}{\sqrt{n}} \sum_{i=1}^{n} (X_i - \mu) \to N(\mu, \sigma)$`

4. `$\frac{\bar{X}_n - \mu}{\sigma} \to N \left(0, \frac{1}{\sqrt{n}} \right)$`

5. `$\sqrt{n} (\bar{X}_n - \mu) \to N(0, \sigma^2)$`

6. `$\frac{1}{\sqrt{n}} \sum_{i=1}^{n} (X_i - \mu) \to N(0, \sigma^2)$`

7. `$\frac{1}{\sqrt{n}} \sum_{i=1}^{n} \left(\frac{X_i - \mu}{\sigma}\right) \to N(0, 1)$`

8. `$\frac{1}{\sqrt{n}} \sum_{i=1}^{n} X_i \to N(\mu, \sigma^2)$`

9. `$\frac{\left(\sum_{i=1}^{n} X_i\right) - n \mu}{\sigma \sqrt{n}} \to N(0, 1)$`

10. `$\frac{\bar{X}_n - \mu}{\sigma} \to N \left(0, \frac{1}{n} \right)$`

---

Solution:

All of the answers with  on the right-hand-side (RHS) are incorrect because the limit on the left is taken as $n\rightarrow \infty$. Also the asymptotic variance from the CLT is $\sigma^2$ and not $\sigma$, so the third response is wrong. The eighth answer is wrong as can be seen by calculating the expectation of the left-hand-side and comparing with the right-hand-side mean $\mu$. The remaining answers are correct, as can be seen by algebraic manipulations applied to the CLT stated in class.

## 3. (Optional) Hoeffding's Inequality

{{< video label="3. (Optional) Hoeffding's Inequality" mp4="videos/3. (Optional) Hoeffding's Inequality.mp4" >}}
