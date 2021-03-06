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
- Text summery

# Pain Point
- **Unbalanced data set**
In big company. There's enough data set show the customer has churn issue. However it doesn't mean they'll all complain on customer service.
- **Interpretable model**
	NLP problem and deep learning, 
- **Integration with other data**
- **Long review** 
	This problem involve topic modeling/summarization issue.

- **Zero-shot discovery of typical user types**
- **Transcript doesn't work well**

- **Handling correlated multi-dimensional behavior data**

- **Model explainability**
- **Evaluate the solution in production**
#  Solution/Paper review
## [I Know You’ll Be Back: Interpretable New User Clustering and Churn Prediction on a Mobile Social Application](http://hanj.cs.illinois.edu/pdf/kdd18_cyang.pdf)


- Track 1 month snapchat new register account information to predict user behavior

| ID | Name Feat. | Description |
|----|-----------------|---------------------------------------|
| 0 | chat_received | textual messages received by the user |
| 1 | chat_sent | textual messages sent by the user |
| 2 | snap_received | snap messages received by the user |
| 3 | snap_sent | snap messages sent by the user |
| 4 | story_viewed | stories viewed by the user |
| 5 | discover_viewed | discovers viewed by the user |

- Doing cluster on user([*cluschurn*]([https://github.com/yangji9181/ClusChurn](https://github.com/yangji9181/ClusChurn))). 
- Build LSTM model predict sequence behavior
## [Text Classification by Bootstrapping with Keywords, EM and Shrinkage](https://www.aclweb.org/anthology/W99-0908.pdf) 
 This is 1999 paper. Pretty old. But it do provide a solution to generate sample set. Dealing with unbalanced issue.
## Implement text summarization. *Pick the important sentences.*
# Sample code

# Terminology
- LTV [life time value](https://baike.baidu.com/item/LTV/10692626)

- ROI [_Return On Investment_](https://wiki.mbalib.com/zh-tw/%E6%8A%95%E8%B5%84%E5%9B%9E%E6%8A%A5%E7%8E%87)
 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTkzNTk0MDM2MiwtMTAxNDI3MDAxMyw1NT
UyMjcxMywtMjE0MTk3NzE2NCwxMDI2NjExNDM4LC01Mzk1NTM5
MjksMTU1NTIzNDEyNyw2MzM2NTE4MjQsLTEyNjgxNTkyMDAsLT
M3MDczMjMzOCwtMTA3NzM0OTMxMiw5NTgxNDM3MDEsNjcwMjQ1
MTE3LDY5MzQ1MDE2NCw1MDkyMjIwODksLTE3NTAwMzQ5MjJdfQ
==
-->