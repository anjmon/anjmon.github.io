+++
title = "Introduction to Time Series"
date = "2024-09-09"
description = "Examples Objectives and some simple models in Time Series Analysis"
tags = [
    "time-series",
    "data-science", "math"

]
math=true
draft=true
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

$$
P[X_1 < x_1, ... X_n < x_n ]  \hspace{2em}   n = 1,2, \ldots
$$







### References

- Brockwell, P. J., & Davis, R. A. (2016). Introduction to time series and forecasting (3rd ed.). Springer.