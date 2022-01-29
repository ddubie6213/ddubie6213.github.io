---
layout: posts
title:  "(4) Random Process"
categories: prob
author_profile: false
use_math: true
sidebar:
    nav: "docs"
---

# Definition of Random Process
If every outcome $x_i \ \in \ S$ is related to the certain rule depending on time, $X$ is able to be modeled for time to $\mathit{t}$ and outcome to $\xi$ and it is given by
$$
    X(t, \ \xi) \qquad t \ \in \ I
$$

The graph of the function $X(t, \ \xi$ versus t, for $\xi$ fixed, is called a **realization sample paht**, or **sample function** of the random process. Thus we can view the outcome of the random experiment as producing an entire function of time as shown below.

![trans](/assets/img_prob/prob2.png)

Note the figure above. At certain time $t \ = T$, the sample functions follow a random variable(i.e If time is fixed, the outcomes follow the certain distribution.) This ensemble of the function is called a **random process**.

# Specifying a Random Process
##### Joint Distributions of Time Samples
Let $X_1, \ X_2, \ldots, \ X_n$ be the k random avriables obtained by sampling the random process $X(t, \ \xi)$ at the times $t_1, \ t_2, \ldots, t_k$ 
The joint cdf of the time from the time $t_1$ to $t_n$ is given by
$$
    F_{X_1, \ X_2, \ \ldots, \ \X_n}(x_1, \ x_2, \ldots, \ x_n) \ = \ P[X_(t_1) \ \leq \ x_1, \ X(t_2) \leq \ x_2, \ \ldots, \ X(t_k) \ \leq \ x_n]
$$
also, the joint pdf is given by
$$
    f_{X_1, \ X_2, \ldots, \ X_n}(x_1, \ x_2, \ \ldots, \ x_n) \ = \ \dfrac{\partial}{\partial x_1}\dfrac{\partial}{\partial x_2}\ \ldots \ \dfrac{\partial}{\partial x_n}F_{X_1, \ X_2, \ \ldots, \ \X_n}(x_1, \ x_2, \ldots, \ x_n) 
$$

The joint pmf is given by 
$$
    p_{X_1, \ X_2, \ \ldots \ X_n}(x_1, \ x_2, \ \ldots, \ x_n) \ = \ P[X(t_1) \ = x_1, \ X(t_2) \ = \ x_2, \ \ldots \ X(t_k) \ = \ x_k]
$$

# The Mean, Autocorrelation, and Autocovariance Functions
##### Mean Function $m(t)$
$$
    m_X(t) \ = \ E[X(t)] \ = \ \int_{-\infty}^{\infty}x f_{X(t)}(x)dx
$$

##### Variance Function $VAR[X(t)]$
$$
    VAR[X(t)] \ = \ \int_{-\infty}^{\infty}(x \ - \ m_X(t))^2f_{X(t)}(x)dx
$$

##### Autocorrelation $R_X(t1, \ t2)$
$$
    R_{X}(t_1, \ t_2) \ = \ E[X(t_1)X(t_2)] \ = \ \int_{-\infty}^{\infty}xyf_{X(t_1),X(t_2)}(x, \ y)dxdy
$$
##### Autocovariance $C_X(t_1, \ t_2)$
$$
    C_X(t_1, \ t_2) \ = \ E[\{ X(t_1) \ - \ m_X(t_1)\} \{ X(t_2) \ - \ m_X(t_2)  \}]
$$
The expansion the formula above is given by
$$
    \begin{aligned}
            C_X(t_1, \ t_2) \ &= \ E[X(t_1)X(t_2)] - m_{X(t_1)}m_{X(t_2)} \\
                              &= R_X(t_1, \ t_2) \ - \ m_{X(t_1)}m_{X(t_2)}
    \end{aligned}
$$

The variance when time is *t* is given by
$$
    VAR[X(t)] \ = \ C_X(t, \ t)
$$

The formula of distcrete time random process is similar to continuous time R.V. 