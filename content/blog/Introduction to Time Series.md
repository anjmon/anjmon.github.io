+++
title = "Introduction to Time Series"
date = "2024-09-09"
description = "Examples Objectives and some simple models in Time Series Analysis"
tags = [
    "time-series",
    "data-science", "math"

]
math=true
draft=false
+++

## Examples of Time Series

A **time series** is a set of observations $x_t$, at a specific time t. Most examples of time series in the digital format are of the discrete type. Any digital or physical recording of a continuous analog signal can only be performed by sampling and, is hence rendered discrete. So I guess for all practical purposes, we would be mostly dealing with discrete time series. 



{{< figure src="/images/ch1/ex1.png" alt="Sales Plot" width="600" height="300" caption="Fig1. Sales Data" class="figure" figure="1"  >}}

The above is an example of time series data. The time steps aren't at regular intervals. Test



## Time Series Models
 
{{< definition term="Definition 1" >}}

A **time series** model for the observed data $\lbrace x_t \rbrace$ is a specification of the joint
distributions (or possibly only the means and covariances) of a sequence of random
variables $\lbrace X_t \rbrace$ of which $\lbrace x_t\rbrace$ is postulated to be a realization.

(Brockwell & Davis, 2016)

{{< /definition >}}

The nature of the models that we deal with are probabilistic because of the presence of some stochasticity, either due to an unknown input or due 
to the process of measurement itself. 

An ideal time series model would specify the joint probability distributions at all time steps. $ \big( t \epsilon  \lbrace 1,2 ... n \rbrace \big)$

i.e. all the probabilities,

$$P[X_1 < x_1, ... X_n < x_n ]  \hspace{2em}   n = 1,2, \ldots $$

Practically, it isn't possible to model the joint probabilities due to the large number of parameters that it would create. Instead we we look at the
1st and 2nd order moments $ E(X_t) \text{ and } E(X_tX_{t+h})$ , $ t = 1,2,...$ and $h = 0,1,2...$



**Example 1- iid Noise**


For iids,

$$ P[X_1\leq x_1,\dots X_n \leq x_n ] = F(x_1)\dots F(x_2)$$

where, F is the cumulative distribution function.

A function that minimises the mean squared error $E\Big[ \Big(X_{n+h} - f(X_1,\dots , X_n)\Big)^2\Big] $ is 0.



### Trend

For models with trend (upward or downward), we can consider the following form:

$$ X_t = m_t + Y_t
$$

Where $m_t$ is a slowly changing component known as trend and $Y_t$ has zero mean.

A useful approach for estimating $m_t$ is the method of least squares.

In the least squares procedure we attempt to fit a parametric famaliy of functions,

e.g.,  $m_t =  a_0 + a_1t + a_2t^2$

to the data $\lbrace x_1,x_2...,x_n \rbrace$ by choosing the parameters to minimize  $\sum_{t=1}^{n} (x_t - m_t)^2 $

This method is called least squares regression.

### Seasonality

For seasonal factors, we can consider the following model,

$$ X_t = s_t + Y_t $$


Since $s_t$ is a periodic function of t, a convenient choice for $s_t$ is a sum of harmonics given by,

$$ s_t = a_0 + \sum_{j=1}^k (a_jcos(\lambda_jt) + b_jsin(\lambda_jt))
$$


The coefficients fo the above model can be obtained by something called **Harmonic Regression.** I might go into the details of Harmonic Regression in some other post. Even I am yet to fully understand it. For now I have included a reference.
### References

- Brockwell, P. J., & Davis, R. A. (2016). Introduction to time series and forecasting (3rd ed.). Springer.
-  http://www-stat.wharton.upenn.edu/~stine/stat910/lectures/06_harmonic_regr.pdf