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



# Paper solution
- [I Know You’ll Be Back: Interpretable New User Clustering and Churn Prediction on a Mobile Social Application](http://hanj.cs.illinois.edu/pdf/kdd18_cyang.pdf)


- [Text Classification by Bootstrapping with Keywords, EM and Shrinkage](https://www.aclweb.org/anthology/W99-0908.pdf) 
	This is 1999 paper. Pretty old. But it do provide a solution to generate sample set. Dealing with unbalanced issue.
# Sample code
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyNjgxNTkyMDAsLTM3MDczMjMzOCwtMT
A3NzM0OTMxMiw5NTgxNDM3MDEsNjcwMjQ1MTE3LDY5MzQ1MDE2
NCw1MDkyMjIwODksLTE3NTAwMzQ5MjJdfQ==
-->