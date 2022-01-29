---
layout: posts
title:  "(3) Sums of Random Variables and Long-Term Averages"
categories: prob
author_profile: false
use_math: true
sidebar:
    nav: "docs"
---

# Sums of Random Variables
Let $X_1, \ X_2, \ \ldots, \ X_n$ be a sequence of random variables, and let $S_n$ be their sum :

$$
    S_n \ = \ X_1 \ + \ X_2 \ \ldots \ X_n
$$

###### Mean of $S_n$
The expectation of the sum of n random variables is below :
$$
    E[X_1 \ + \ X_2 \ + \ \ldots \ X_n] \ = \ E[X_1] \ + \ E[X_2] \ + \ \ldots \ E[X_n]
$$

###### Varaiance of $S_n$
$$
    \begin{aligned}
        VAR(S_n) \  &= \ E[(S_n \ - \ E[S_n])^2] \\
                    &= \ E[(\sum_i X_i \ - \ \sum_i E[X_i])^2] \\
                    &= \ E[(\sum_i (X_i \ - \ E[X_i]))^2] \\
                    &= \ \sum_j \sum_k E[(X_j \ - \ E[X_j])(X_k \ - \ E{X_k})] \\
                    &= \ \sum_k E[(X_k \ - \ E[X_k])^2] \ + \ \sum_j\sum_i COV(X_j, X_i)    \qquad (i \ \neq \ j)
    \end{aligned}
$$

If $X_1, \ X_2, \ \ldots, \ X_n$ are *independent random variables*, then $COV(X_j, \ X_k) \ = \ 0$ for $j \ \neq k$ and
$$
    VAR(X_1 \ + \ X_2 \ \ldots \ X_n) \ = \ VAR(X_1) \ + \ VAR(X_2) \ + \ \ldots \ + \ VAR(X_n)
$$

##### PDF os Sums of Independent Random Variables
Let $S_n$ is the sum of independent n number of random variables. The characteristic function $\Phi_{S_n}$ :

$$
    \begin{aligned}
        \Phi_{S_n} \    &= \ E[e^{jw S_n}] \\
                        &= \ E[e^{jw(X_1 \ + \ X_2 \ + \ \ldots \ + \ X_n)}] \\
                        &= \ E[e^(jw X_1)]E[e^(jw X_2)] \ \ldots \ E[e^(jw X_n)] \\
                        &= \ \Phi_{X_1}(w_1)\Phi_{X_1}(w_2)\ \ldots \ \Phi_{X_n}(w_n)
    \end{aligned}
$$

The formula above yields

$$
    f_{S_n} \ = \ \mathbb{f}^{-1} \{ \Phi_{X_1}(w_1)\Phi_{X_2}{w_2} \ \ldots \ \Phi{X_n}{w_n} \}
$$

# The Sample Mean and the Laws of Large Numbers
Let X be a random variable for which the mean, $E[X] \ = \ \mu$ is unknwn. Let $X_1, \ \ldots \ X_n$ denote n independent, repeated measurement of X; that si, the $X_j$'s are **independent, identically distributed(iid)** random variables with the same pdf as X.
Then, the **sample mean** of the sequence is used to *estimaite* $E[X]$ :

$$
    M_n \ = \ \dfrac{1}{n}\sum_{j=1}^n X_j
$$


##### Mean
The expected value of the sample mean is given by 

$$
    E[M_n] \ = \ E \big[\dfrac{1}{n} \sum_{j=1}^n X_j \big] \ = \ \dfrac{1}{n}\sum_{j=1}^n \ = \ \mu
$$

Note **sample mean* is an **unbiased estimator* for $\mu$, therefore we need to find variance of $M_n$

##### Variance
The variance of sample mean is given by

$$
    E[(M_n \ - \ \mu)^2] \ = \ E[(M_n \ - \ E[M_n])^2]
$$

$Because X_1, \ X_2, \ \ldots \ X_n$ are iid, $COV(X_i, \ X_j)$ for $i \ \neq \ j$ and this fact yields
$$
    VAR[M_n] \ = \ \dfrac{1}{n^2}VAR[S_n] \ = \ \dfrac{n\sigma^2}{n^2} \ = \ \dfrac{\sigma^2}{n}
$$

###### Week Law of Large Numbers
Let $X_1, \ X_2, \ \ldots$ be a sequence of iid random variables with ifnite mean $E[X_n] \ = \ \mu$, then for $\epsilon \ > \ 0$

$$
    \lim_{n\rightarrow\infty}P[\vert M_n \ - \ \mu \vert \ < \ \epsilon] \ = \ 1
$$

###### Strong Law of Large Number

$$
 \lim_{n\rightarrow\infty}P[\vert M_n \ = \ \mu] \ = \ 1
$$

# The Central Limit Theorem
Let $X_1, \ X_2, \ $ be a sequence if iid random variables with finite mean $\mu$ and finite variance $\sigma^2$, and let $S_n$ be the sum of the first n random variable in the sequence :
$$
    S_n \ = \ X_1 \ + \ X_2 \ + \ \ldots \ + \ X_n
$$
then, the cdf of a properly normalized $S_n$ approaches that of a *Gaussian random variable*.
Let $Z_n$ be a normalized gaussian variable of $S_n$ for $n\rightarrow\infty$, $Z_n$ is given by 
$$
    Z_n \ = \ \dfrac{S_n \ - \ n\mu}{\sigma \sqrt{n}}
$$
then
$$
    \lim_{n\rightarrow\infty}P[Z_n \ \leq \ z] \ = \ \int_{-\infty}^{z}e^{-x^2 / 2}dx
$$

**proof)** Find the reason $Z_n$ approaches to *Gaussian Random Variable*

$$
    Z_n \ = \ \dfrac{S_n \ - \ n\mu}{\sigma\sqrt{n}} \ = \ \dfrac{1}{\sigma\sqrt{n}}\sum_{k=1}^n(X_k \ - \ \mu)
$$
The characteristic function of $Z_n$ is given by
$$
    \begin{aligned}
        \Phi_{Z_n}(w) \ &= \ E \big[e^{jw Z_n} \big] \\
                        &= \ E \Bigg[ exp\{ \dfrac{jw}{\sigma\sqrt{n}} \sum_{k=1}^{n}(X_k \ - \mu) \}\Bigg] \\
                        &= \ E \Bigg[ \prod_{k=1}^n e^{jw(X_k \ - \ \mu)/\sigma\sqrt{n}} \Bigg] \\
                        &= \prod_{k=1}^n E[e^{jw(X_k \ - \ \mu) / \sigma\sqrt{n}}] \\
                        &= \{ E[e^{jw(X \ - \ \mu)/\sigma\sqrt{n}}] \}^n
    \end{aligned}
$$

As expanding $E[e^{jw(X \ - \ \mu)/\sigma\sqrt{n}}]$ by *Taylor Series*
$$
    \begin{aligned}
        E[e^{jw(X \ - \ \mu)/\sigma\sqrt{n}}] \ &= \ E \Bigg[ 1 \ + \  \dfrac{jw}{\sigma\sqrt{n}}(X \ - \ \mu) \ + \ \dfrac{(jw)^2}{2!n\sigma^2}(X \ - \ \mu)^2 \ + \ R(w) \Bigg] \\
                                                &= \ 1 \ + \ \dfrac{jw}{\sigma\sqrt{n}}E[(X \ - \ \mu)] \ + \ \dfrac{(jw)^2}{2!n\sigma^2}E[(X \ - \ \mu)^2] \ + \ E[R(w)] \\
                                                &\backsimeq \ 1 \ - \ \dfrac{w^2}{2n} \ + \ E[R(w)] \qquad for \qquad E[(X \ - \ \mu)] \quad and \quad E[(X \ - \ \mu)^2] \ = \ \sigma^2
    \end{aligned}
$$
The term $E[R(w)]$ converges to zero if $n\rightarrow\infty$. Therefore, if the sufficient number of sample collected,
$$
    \begin{aligned}
        \Phi_{Z_n}(w) \ &= \ \Bigg\{ 1 \ - \ \dfrac{w^2}{2n}\Bigg\}^n \\
                        &\rightarrow \ e^{-w^2/2} \ \ as \ \ n\rightarrow\infty
    \end{aligned}
$$
