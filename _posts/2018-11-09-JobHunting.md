---
layout:     post
title:      DS Question Collection-A/B Test
subtitle:   Failue doesn't deafeat you
date:       2018-11-09
author:    Chester
header-img: img/failure.jpg
catalog: true
tags:
    - Job
---


## A/B testing & Interview Question



### Terminology

#### What's P-value?

The p-value is the probability of observing a value as or more extreme than the one observed under the Null Hypothesis.

#### What is a confidence interval and how do you interpret it?
```python
def get_ci(value, cl, sd):
    loc = stats.norm.ppf(1 - cl/2)
    rng_val = sci.norm.cdf(loc - value/sd)

    lwr_bnd = value - rng_val
    upr_bnd = value + rng_val 

    return_val = (lwr_bnd, upr_bnd)
    return(return_val)
```

#### What’s the difference between a MAP, MOM, MLE estima-
tor? In which cases would you want to use each?




### Specical Case

## Design Problem
#### Desgin A A/B test 
Here's real problem I've enconterd and failed like idot. 
> Assume we are the a platform provide the suggestion on Cloth style 
> There are two color we need to decide whtich one is better?
> That's say we can only test 1000 time, how you design the experiment??

#### Too Many Variants?
```python
import scipy.stats as stats
import numpy as np
import matplotlib.pyplot as plt
% matplotlib inline

```
#### What would be the hazards of letting users sneak a peekat the other bucket in an A/B test?


#### In an A/B test, how can you check if assignment to the various buckets was truly random?

It's almost impossible to test randomness on statstic. However we can do another trial. We can try to test equivalence for the A/B two part. That's some time we call** A/A test**.

Here's an example to show how A/A test going.




#### How would you run an A/B test if the observations areextremely right-skewed?



## Refernce

Strongly recommend to read These as source:

[10 Statistics Traps in A/B Testing: The Ultimate Guide for Optimizers](https://conversionxl.com/blog/testing-statistics-mistakes/)

[What is an A/A Test](https://conversionsciences.com/blog/aa-test-gives-you-confidence/)

[The Math behind A/B Testing](https://towardsdatascience.com/the-math-behind-a-b-testing-with-example-code-part-1-of-2-7be752e1d06f)
