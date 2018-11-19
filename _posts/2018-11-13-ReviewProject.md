---
layout:     post
title:      MakeUp Product Review Analysis
subtitle:   Scrapy + python
date:       2018-06-12
author:    Chester
header-img: img/makeup_title.jpeg
catalog: true
tags:
    -Project
---


## Idea?
THis is poject we developed on **Online Social media Analysis**. 
In the begining idea is very easy. My friend Tina want to know which makeup product is most popular right now. 

However, we realize we need to define what is **popular**? And there's another question following: Is the number of review mean better?

We plan to build a real-time product review analysis system that performs a review time series plot for Sephora and Twitter and predicted
rating based on Twitter reviews. 

Ok! 

Let's dive into review




## Roughly Saying the process
Scraped Sephora product and review first to
the system, and put them in the review database. Then it
does vectorize with these reviews, which can extract frequent
features in opinion words. In the last two-step, all the features
are analyzed in data modeling and a final predicted rating is
produced.
<img  height="300" src="Ok! 

Let's dive into review

![FLOWCHART](../img/flowchart_review.png">|width=100)


## Data collection
Here's I don't provide the details on how we crawling the data. I should put it into another post.

I want to explanin why we need and how we use those data.

## Pain points
#
## There's too many review
#### Aprori
#### LDA


### There's only few review

E-Commence is becoming more and more popular,
the number of customer reviews that a product receives grows
rapidly. Popular products can get hundreds or even thousands
reviews, however, some special products get none reviews if they
are not launched on e-commerce. This makes it difficult for a
potential customer to choose them. Therefore, we proposed the
method which can help customers to find their preferred product
more efficiently.In this paper, we present Makeup Reviews
Engine, a real-time product review analysis system that performs
a review time series plot for Sephora and Twitter and predicted
rating based on Twitter reviews. We also summarize aspects
of product reviews. We evaluate the accuracy of the system
through RMSE (root-mean-square error) and the approach in
the experiment. The result shows that predicted rating on Twitter
is really closed to Sephora product rating. It also successfully
extracts product summary from product review.


## Keep On the Trail?

In the end we develop something we don't expect in the begining. I need to ask myself. Do we actually provide any value for user? Can anyone get anything from this? 

I think it's not.

We make too many assumption let make the project going. We can't overcome some essensial problem in this.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI1NDA3OTI0NF19
-->