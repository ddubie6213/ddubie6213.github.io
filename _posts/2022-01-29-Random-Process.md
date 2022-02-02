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

The graph of the function $X(t, \ \xi)$ versus t, for $\xi$ fixed, is called a **realization sample path**, or **sample function** of the random process. Thus we can view the outcome of the random experiment as producing an entire function of time as shown below.

![trans](/assets/img_prob/prob2.png)

Note the figure above. At certain time $t \ = T$, the sample functions follow a random variable(i.e If time is fixed, the outcomes follow the certain distribution.) This ensemble of the functions is called a **random process**.

# Specifying a Random Process
##### Joint Distributions of Time Samples
Let $X_1, \ X_2, \ldots, \ X_n$ be the k random avriables obtained by sampling the random process $X(t, \ \xi)$ at the times $t_1, \ t_2, \ldots, t_k$ 
The joint cdf of the time from the time $t_1$ to $t_n$ is given by

$$
    F_{X_1, \ X_2, \ \ldots, \ X_n}(x_1, \ x_2, \ldots, \ x_n) \ = \ P[X_(t_1) \ \leq \ x_1, \ X(t_2) \leq \ x_2, \ \ldots, \ X(t_k) \ \leq \ x_n]
$$

also, the joint pdf is given by

$$
    f_{X_1, \ X_2, \ldots, \ X_n}(x_1, \ x_2, \ \ldots, \ x_n) \ = \ \dfrac{\partial}{\partial x_1}\dfrac{\partial}{\partial x_2}\ \ldots \ \dfrac{\partial}{\partial x_n}F_{X_1, \ X_2, \ \ldots, \ X_n}(x_1, \ x_2, \ldots, \ x_n) 
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

##### Autocorrelation $R_X(t_1, \ t_2)$
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

##### Cross-correlation $R_{X, \ Y}$

$$
    R_{X, \ Y} \ = \ E[X(t_1)Y(t_2)]
$$
The processes $X(t_1)$ and $Y(t_2)$ are called **orthgonal** if $R_{X, \ Y}(t_1, \ t_2) \ = \ 0$. 

##### Cross-covariance $C_{X,Y}(t_1. \ t_2)$
$$
    \begin{aligned}
        C_{X, \ Y} \ &= \ E[\{ X(t_1) \ - \ m_X(t_1) \} \{ Y(t_2) \ - \ m_X(t_2) \}] \\
                     &= R_{X, \ Y}(t_1, \ t_2) \ - \ m_X(t_1)m_Y(t_2)
    \end{aligned}
$$
The processes $X(t)$ and $Y(t)$ are **uncorrelated** if $C_{X, \ y}(t_1, \ t_2) \ = \ 0$ for all $t_1$ and $t_2$.

# Discret-Time Processed : Sum Process, Binomial Counting Process and Random Walk
#### iid Random Prcoess
- The mean of an iid process
  $m_x(n) \ = \ E[X_n] \ = \ m$
- Autocovariance
  $$
  \begin{aligned}
    C_X(n_1, \ n_2) \ &= \ E[(X_{n_1} \ - \ m)(X_{n_2} \ - \ m] \\
                      &= \ 0        \qquad  \qquad  (for \ \ n_1 \ \neq \ n_2)
  \end{aligned}
  $$

#### Independent Increments and Markov Properties of Random Processed
If the increments in disjoint intervals are **independent random variables**, a random process $X(t)$ is called **independent increment**.
For example, the random variables sampled from the random process X at $t_1, t_2 \ \ldots \ ,t_k$ denote $X(t_1), \ \ldots \ X(t_k)$.
For $t_1 \ < \ \ldots \ < t_k$, the differnces of the random variables are given by
$$
    X(t_2) \ - \ X(t_1), \quad X(t_3) \ - \ X(t_2), \ \ldots \, \ X(t_k) \ - \ X(t_{k-1})
$$
If the terms above are independent, the random varible X is called $independent increment$.

###### Markov Property
Let $t_1 \ < \ \ldots \ < \ t_k$ and if random process $X(t)$ satisfies the property given by
$$
    f_{X(t_k)}(x_k \ | \ X(t_{k-1}) \ = \ x_{k-1}, \ \ldots, \ X(t_1) \ = \ x_1) \ = \ f_{X(t_k)}(x_k \ | \ X(t_{k-1}) \ = \ x_{k-1})
$$
the random process X(t) has ***Markov Property*.

###### Sum Process
The sum of a sequence of iid random variables, $X_1, \ X_2, \ldots$ is given by
$$  
    \begin{aligned}
        S_n \   &= \ X_1 \ + \ X_2 \ + \ \ldots \ + \ X_n     \qquad \quad n \ = \ 1, \ 2, \ \ldots \\
                &= \ S_{n-1} \ + \ X_n
    \end{aligned} 
$$

The sum process $S_n$ has **independent increments** in nonoverlapping time intervals.
The increments of $S_n$ in these disjoint time intervals for $n_0 \ < \ n \ \leq \ n_1$, $n_2 \ < \ n \ \leq \ n_3$ and $n_1 \ \leq \ n_2$ are given by

$$
        \begin{aligned}
            S_{n_1}  \ - \ S_{n_0} \ &= \ X_{n_0+1} \ + \ \ldots \ X_{n_1} \\
            S_{n_3}  \ - \ S_{n_2} \ &= \ X_{n_2+1} \ + \ \ldots \ X_{n_3}
        \end{aligned}
$$

The random variables $S_{n_1}  \ - \ S_{n_0}$ and $S_{n_3}  \ - \ S_{n_2}$ have no overlap, they are independent.
Futhermore, they are sum of *iid* random variables, so the property below is satisfied.

$$
    \begin{aligned}
        P[S_{n^{'}} \ - \ S_n \ = \ y] \ = \ P[S_{n^{'} \ - \ n} \ = \ y]
    \end{aligned}
$$
The property above is called **stationary increment** and this property means the origin is not important.

# Poisson and Associated Random Processes
A random process $X(t)$ is a **Gaussian random process** if the samples $X_1 \ = \ X(t_1), \ X_2 \ = \ X(t_2), \ldots, \ X_k \ = \ X(t_k)$ are jointly Gaussian random variables for all $k$, and all choices of $t_1, \ \ldots, \ t_k$.
Gaussian random process is given by
$$
    \begin{aligned}
        f_{X_1, \ X_2, \ \ldots, \ X_k}(x_1, \ x_2, \ \ldots, \ x_k) \ &= \ \dfrac{exp(-\dfrac{1}{2}(\mathbf{x}-\mathbf{m})^T K^{-1}(\mathbf{x}-\mathbf{m}))}{(2\pi)^{k/2}\vert K \vert^{1/2}}
    \end{aligned}
$$
The **mean vector** and **covariance matrix** are given by
$$
    \begin{aligned}
        \mathbf{m} \ = \ \begin{Bmatrix}
            m_X(t_1) \\ \vdots \\ m_X(t_k)
        \end{Bmatrix}
    \qquad
    K \ = \ \begin{Bmatrix}
        C_X(t_1, \ t_1) & C_X(t_1, \ t_2) & \ldots & C_X(t_1, \ t_k) \\
        C_X(t_2, \ t_1) & C_X(t_2, \ t_2) & \ldots & C_X(t_2, \ t_k) \\
        \vdots          &   \vdots        & \ddots &  \vdots         \\
        C_X(t_k, \ t_1) & \ldots          & \ldots & C_X(t_k, \ t_k) 
    \end{Bmatrix}
    \end{aligned}
$$

# Stationary Random Processes
A *discrete-time* or *continuous-time* random process X(t) is **stationery** if the joint distribution of any set of samples does not depend on the placement of the time origin. This means that the joint cdf of $X(t_1), \ X(t_2), \ \ldots, \ X(t_k)$ is the same as that of $X(t_1 \ + \ \tau), \ X(t_2 \ + \ \tau), \ \ldots, \ X(t_k \ + \ \tau)$ :

$$
\begin{aligned}
    F_{X(t_1), \ldots,X(t_k)}(x_1, \ \ldots, \ x_k) \ &= \ F_{X(t_1+\tau), \ \ldots, \ X(t_k+\tau)}(x_1, \ \ldots, \ x_k)
\end{aligned}
$$

# Wide-Sense Stationary Random Processed
Two condtions of *Wide-Sense Staionary*(WSS)
- $F_{X(t_1), \ldots,X(t_k)}(x_1, \ \ldots, \ x_k) \ = \ F_{X(t_1+\tau), \ \ldots, \ X(t_k+\tau)}(x_1, \ \ldots, \ x_k)$
- $m_X(t) \ = \ m$ *for* all $t$
  
The property below is satisfied because of the conditions above.
Let $\vert t_1 \ - t_2 \vert \ = \ \tau$
- $C_X(t_1, \ t_2) \ = \ C_X(\tau)$
- $R_X(t_1, \ t_2) \ = \ R_X(\tau)$



# Reference

>Garcia, *Probability, Statistics, and Random Processes for Electrical Engineering* PEARSON(2009) p499-568