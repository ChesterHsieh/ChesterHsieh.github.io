# Define the problem
Customer churn occurs when customers or subscribers stop doing business with a company or service. 

All the telecom/cable/tv services need to know what happen. 
**Why** the customer leave?
**When** they gonna leave? 
**How** they change their mind? Explicitly “retention-first” care strategy or marketing strategy to hedge against their risk of leaving.

If the service is subscription type business. For example e-commerce. Customer don't need to pay periodically. Another question comes out.
**How** to define the churn?

Everyone new to this problem should take look on [Kaggle data](https://www.kaggle.com/blastchar/telco-customer-churn) first. There are already good solution on predict. This post is trying to target text data.

## NLP source
Call log/Email/Online assistance (CRM)history are the three major resource the company can utilize. Do you remember every time you call for customer service you'll heard **For quality purpose, this call might be recorded**. 

Except that, When customer don’t receive exceptional customer service and experiences, they flock to competitors and share their negative experiences on [social media](https://www.salesforce.com/blog/2015/01/ten-customer-service-stats-what-they-mean-your-contact-center-gp.html): 59% of 25-34-year-olds share poor customer experiences online.

## Ideas of solving problem
- Social media monitoring
- Voice of employee/turnover prevention
- Voice of Customer (VoC) & Customer Experience Management
- 

# Pain Point
**Unbalanced data set**
In big company. There's enough data set show the customer has churn issue. However it doesn't mean they'll all complain on customer service.

**Integration with other data**
**Very long review**
**

**Zero-shot discovery of typical user types**

**Handling correlated multi-dimensional behavior data**

**
# Paper solution
- [I Know You’ll Be Back: Interpretable New User Clustering and Churn Prediction on a Mobile Social Application](http://hanj.cs.illinois.edu/pdf/kdd18_cyang.pdf)
Doing cluster on user([*cluschurn*]([https://github.com/yangji9181/ClusChurn](https://github.com/yangji9181/ClusChurn))). -> 6 user type + churn data -> LSTM+attention ->

- [Text Classification by Bootstrapping with Keywords, EM and Shrinkage](https://www.aclweb.org/anthology/W99-0908.pdf) 
	This is 1999 paper. Pretty old. But it do provide a solution to generate sample set. Dealing with unbalanced issue.
# Sample code

# Terminology
- LTV [life time value](https://baike.baidu.com/item/LTV/10692626)
- Churn probability
- Port out probability for individual competitors
- median remaining tenure
- Churn triggers
- 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTYxNzM1MDUzNCw2MzM2NTE4MjQsLTEyNj
gxNTkyMDAsLTM3MDczMjMzOCwtMTA3NzM0OTMxMiw5NTgxNDM3
MDEsNjcwMjQ1MTE3LDY5MzQ1MDE2NCw1MDkyMjIwODksLTE3NT
AwMzQ5MjJdfQ==
-->