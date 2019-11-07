# Define the problem
Customer churn occurs when customers or subscribers stop doing business with a company or service. 

All the telecom/cable/tv services need to know what happen. 
**What** kind of people will leave? Customer segmentation
**Why** the customer leave?  Identify churn triggers.
**When** they gonna leave? 
**How** they change their mind? Treat cost/effect estimation
Explicitly “retention-first” care strategy or marketing strategy to hedge against their risk of leaving.


Everyone new to this problem should take look on [Kaggle data](https://www.kaggle.com/blastchar/telco-customer-churn) first. There are already good solution on predict. This post is more focus on how to utilize NLP data on churn problem.


## NLP source
Call log/Email/Online assistance (CRM)history are the three major resource the company can utilize. Do you remember every time you call for customer service you'll heard **For quality purpose, this call might be recorded**. 

Except that, When customer don’t receive exceptional customer service and experiences, they flock to competitors and share their negative experiences on [social media](https://www.salesforce.com/blog/2015/01/ten-customer-service-stats-what-they-mean-your-contact-center-gp.html): 59% of 25-34-year-olds share poor customer experiences online.

## Ideas of solving problem
- Social media monitoring
- Voice of employee/turnover prevention
- Voice of Customer (VoC) & Customer Experience Management
- 

# Pain Point
- **Unbalanced data set**
In big company. There's enough data set show the customer has churn issue. However it doesn't mean they'll all complain on customer service.

- **Integration with other data**
- **Long review** 
	This problem involve topic modeling/summarization issue.

- **Zero-shot discovery of typical user types**

- **Handling correlated multi-dimensional behavior data**

- **Model explainability**
- **Evaluate the solution in production**
# Paper solution
- [I Know You’ll Be Back: Interpretable New User Clustering and Churn Prediction on a Mobile Social Application](http://hanj.cs.illinois.edu/pdf/kdd18_cyang.pdf)
Doing cluster on user([*cluschurn*]([https://github.com/yangji9181/ClusChurn](https://github.com/yangji9181/ClusChurn))). -> 6 user type + churn data -> LSTM+attention ->

- [Text Classification by Bootstrapping with Keywords, EM and Shrinkage](https://www.aclweb.org/anthology/W99-0908.pdf) 
	This is 1999 paper. Pretty old. But it do provide a solution to generate sample set. Dealing with unbalanced issue.
# Sample code

# Terminology
- LTV [life time value](https://baike.baidu.com/item/LTV/10692626)

- ROI [_Return On Investment_](https://wiki.mbalib.com/zh-tw/%E6%8A%95%E8%B5%84%E5%9B%9E%E6%8A%A5%E7%8E%87)
 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTUzOTU1MzkyOSwxNTU1MjM0MTI3LDYzMz
Y1MTgyNCwtMTI2ODE1OTIwMCwtMzcwNzMyMzM4LC0xMDc3MzQ5
MzEyLDk1ODE0MzcwMSw2NzAyNDUxMTcsNjkzNDUwMTY0LDUwOT
IyMjA4OSwtMTc1MDAzNDkyMl19
-->