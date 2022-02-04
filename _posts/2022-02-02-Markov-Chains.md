---
layout: posts
title:  "(5) Markov Chains"
categories: prob
author_profile: false
use_math: true
sidebar:
    nav: "docs"
---

# Markov Process
A random process $X(t)$ is a **Markov process** if the futre of the process given the present is independent of the past, that is, if for arbitrary times $t_1 < \ < t_2 \ < \ \ldots \ t_k \ < \ t_{k+1}$

$$
    \begin{aligned}
        P[(X_{k+1} \ = \ x_{k+1} \ | \ X(t_k) \ = \ x_k, \ \ldots \, X(t_1) \ = \ x_1)] \ = \ P[X(t_{k+1} \ = \ x_{k+1} \ | \ x_k)]
    \end{aligned}
$$

Generally, $X_{k+1}$ and $X_k$ respectively denote future and present state.

##### Markov Chain
Let $X(t)$ be a Markov process. The expansion of $X(t)$ is given by

$$
    \begin{aligned}
        P[X(t_{k+1}) \ = \ x_{k+1}, \ X(t_k) \ = \ x_k, \ \ldots, \ X(t_1) \ = \ x_1] \ &= \ \big\{ \prod_{j=1}^k P[X(t_{j+1}) \ = \ x_{j+1} \ | \ X(t_j) \ = \ x_j]  \big\}P[X(t_1) \ = \ x_1]
    \end{aligned}
$$

# Discrete Time Markov Chains
Let $X_n$ be a discrete-time integer-valued Markov chain that starts at $n \ = \ 0$ with pmf
$$
    \begin{aligned}
        p_j(0) \ &\triangleq \ P[X_0 \ = \ j]
    \end{aligned}
$$

Let $P[X_{n+1} \ = \ j \ | \ X_n] \ = \ p_{ij}$ for all $n$. $P[X_n \ = \ i_n, \ldots, \ X_0 \ = \ i_0]$ is

$$

    \begin{aligned}
        P[X_n \ = \ i_n, \ \ldots, \ X_0 \ = \ i_0] \ &= \ p_{i_{n-1}, \ i_n}\ldots p_{i_1, \ i_0}(0)
    \end{aligned}
$$

The state **transition probability matrix** is given by

$$

    P \ = \ \begin{bmatrix}
        p_{00} & p_{01} & p_{02} & \ldots \\
        p_{10} & p_{11} & p_{12} & \ldots \\
         \vdots& \vdots &  \vdots& \ddots
    \end{bmatrix}
$$

Note 

$$ 
    1 \ = \ \sum_j P[X_{n+1} \ = \ j \ | \ X_n \ = \ i] \ = \ \sum_j p_{ij} 
$$

#### The n-step Transition Probabilities
Let $P(n) \ = \ \{ p_{ij}(n) \}$ be *the matrix of n-step transtion probabilities*, wher
$$
    p_{ij}(n) \ = \ P[X_{n+k} \ = \ j \ | \ X_k \ = \ j]    \qquad \qquad (for \  \ n \ \geq \ 0, \ i, \ j \ \geq \ 0)
$$

As $X(t)$ is a *markov process*, note

$$ 
    P[X_{n+k} \ = \ j \ | \ X_k \ = \ i] \ = \ P[X_n \ = \ j \ | \ X_k \ = \ i] 
$$ 

###### Chapman-Kolmogorov Equation
$$
    \begin{aligned}
        p_{ij}(m \ + \ n) \ &= \ \sum_{k}p_{ik}(m)p_{kj}(n)
    \end{aligned}
$$
The matrix of n-step transtion probabilities is given below because of *Chapman-Kolmogorov Equation*.

$$
    \begin{aligned}
        P(n \ + \ m) \ &= \ P(n)P(m)        
    \end{aligned}
$$

###### The State Probabilities
Let $\mathbf{p}(n) \ = \ \{ p_j(n) \}$ denote the row vector of **state probabilities** at itme n.
The probability p_j(n) is related to $\mathbf{p}(n_1)$ by

$$
    \begin{aligned}
        p_j(n) \ &= \ \sum_i P[X_n \ = \ j \ | \ X_{n-1} \ = \ i]P[X_{n-1} \ = \ i] \\
                 &= \ \sum_k p_{ij}p_i(n-1)
    \end{aligned}
$$

The form of the transition matrix $P$and row vector $\mathbf{p}(n-1)$ is given by

$$
    \begin{aligned}
        \mathbf{p}(n) \ &= \ \mathbf{p}(n-1)P   
     \end{aligned}
$$

The result above yields

$$
    \begin{aligned}
        p_j(n) \ &= \ \sum_i P[X_n \ = \ j \ | \ X_0 \ = \ i]P[X_o \ = \ i] \\
                 &= \sum_i p_{ij}(n)p_i(0)
    \end{aligned}
$$

The matrix and vector form is given by

$$
    \mathbf{p}(n) \ = \ \mathbf{p}(0)P(n) \ = \ \mathbf{p}(0)P^n    \qquad \quad for \ \ 1, \ 2 \ \ldots
$$

###### Steady State Probabilities(Convergence)
As $n \ \rightarrow \ \infty$, the n-step transition probability matrix approaches a matrix in which all the rows are equal to the pmf, that is

$$
    p_{ij}(n) \ \rightarrow \ \pi_j \qquad for \ \ all \ i
$$

If the condition above is satisfied, we say that the system is *equilibrium* or *steday state*.
$\pi$ is called **stationary state pmf**.

At the state of equilibrium, the property of $\pi$ is given by

$$
    \begin{aligned}
        \pi_j \ &= \ \sum_i p_{ij}\pi_i \\
        \mathbf{\pi} \ &= \ \mathbf{\pi}P     
    \end{aligned}
$$

Therefore,

$$
    \mathbf{p}(n) \ = \ \pi P^n \ = \ \pi
$$

# Classes of States, Recurrence Properties and Limiting Probabilites

##### Classes of States
- For some $n \ \geq \ 0$, $p_{ij}(n) \ > \ 0$, state i is **accessible** from state j.
- If i and j are **accessible**, i and j **communicate**.   ($i \leftrightarrow j $)

##### Recurrence Properties
Suppose we start a Markov chain in state i, State i is said to be **recurrent** if the process returns to the state with probability one, that is,
$$
    f_i \ = \ P[ever \ \ returning \ \ to \ \ state \ \ i] \ = \ 1
$$
State i is said to be **transient** if

$$
    f_i \ < \ 1
$$

In other words,

$$
    \begin{cases}
        f_i \ = \ 1 & \mathit{state \ i \  \ is \ \ recurrent} \\
        f_i \ < \ 1 & \mathit{state \ i \ \ is \ \ transient}
    \end{cases}
$$

We say that state i has **period** d if it can only reoccur at times that are mutiples of d. On the other hand, we say that state i is **aperiodic** if it has period d = 1.

In other words,
$$
    p_{ii}(n \ + \ kd) \ \neq \ 0 \qquad
    \begin{cases}
        d \ = \ 1 & periodic \quad state    \\
        d \ \neq \ 1 & aperiodic \quad state
    \end{cases}
$$

###### (cf) Possible structures for Markov chains

![markov](/assets/img_prob/prob3.png)

# Limiting Probabilites
![recur](/assets/img_prob/prob4.png)


Suppose we start a Markov chain in a recurrent state i at time n = 0, Let the time that elapses between the (k-1)th and kth returns. The $T_i$ from an iid sequence since each return time is independent of previous return times.

$$
    \text{proportion of time in state i} \ = \ \dfrac{k}{T_i(1) \ + \ T_i(2) \ + \ \ldots + \ T_i(k)}
$$

The **mean recurrence time** is given by

$$
    E[T_i] \ = \ T_i(1) \ + \ T_i(2) \ + \ \ldots + \ T_i(k) \ / \ k
$$

The proportion of time in state is approximated as $\dfrac{1}{E[T_i]} \ \rightarrow \ \pi_i$,
where $\pi_i$ is the *long-term proportion of time* spent in state i.

If $\pi_i \ > \ 0$, *state i* is positive recurrent.

If markov chain that is positive recurrent and aperiodic states, it called **ergodic**.

# Reference

>Garcia, *Probability, Statistics, and Random Processes for Electrical Engineering* PEARSON(2009) p499-568