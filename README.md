# Home Credit Default Risk

## Table of Contents
<ul>
<li><a href="#ack">Acknoledgement</a></li>
<li><a href="#exec">Executive Summary</a></li>
<li><a href="#bg">Background</a></li>
<li><a href="#busund">Business Understanding</a></li>
<li><a href="#dataund">Data Understanding</a></li>
</ul>

<a id='ack'></a>
## ACKNOWLEDGEMENT
Our project on Home Credit Default Risk has been a great learning experience. We were
exposed to a variance of subject matter, concerns and arguments that helped us collectively
assemble and shape the project.

We acknowledge Dr. Prakash Shrivastava under whose guidance we were able to complete
the project and effectively present its valuable benefits.

A greater share of inputs and knowledge from each one of us made this project report
possible to its rightful accuracy.

To all our colleagues who have helped us either directly or indirectly, we are grateful for their
valuable inputs.

<a id='exec'></a>
## EXECUTIVE SUMMARY

Generally, banks and other financial institutions review a person’s credit history to figure out
his/her loan repayment ability. Based on such a review, they decide on whether to sanction
a loan. Many financial institutions do not consider customers without enough credit history
even if they can repay their loans. This unserved portion of the population presents a business
opportunity.

Through the modelling process, we identified the profitable members of this unbanked
population and obtained answers for the key decisions, such as:

1. Which loan applications do we accept?
2. How much loan do we give to an applicant?
3. What demographics do we target our marketing at?

Our data sources consist of internal Data generated by Home Credit and data obtained from
the Credit Bureau, which we downloaded from Kaggle. Our dataset had 102 variables, from
which we selected 19 based on variable importance, domain knowledge, through the removal
of empty observations and multicollinearity. We handled anomalies, outliers and missing
values in the dataset.

We analyzed and broke the data into 5 clusters:

1. High Income Professionals
2. Old-aged Rural Workers
3. Young semi-skilled workers
4. Middle aged semi-skilled workers
5. Unskilled Workers

We ran Logistic regression, Linear regression and decision trees on these clusters. Decision
trees had a very high accuracy on the training data, which we speculated might be due to
overfitting. This was confirmed when we ran those models on validation data. Linear
regression failed to satisfy its assumptions and so, we dropped it. For Logistic regression, we
obtained ideal cut-offs by taking the cost of false negative to be 1.5 times the cost of false
positive and used those cut-offs to aid us in our decisions.
Based on our models, we decided to target our marketing and loan efforts towards High
Income Professionals in general, and its first decile. To a lesser extent, we would also direct
those efforts towards Old-aged Rural Workers, Young semi-skilled workers and Unskilled
Workers.

For future models, we would like to include additional predictors, use dimensionality
reduction techniques such as PCA, and further stunt the growth/prune the decision trees.

<a id='bg'></a>
## BACKGROUND
### a) Domain:
Banking & Finance

Sub: Consumer credit & Loan application

Company in Focus: Home Credit

### b) Brief description of the scenario:
Home Credit strives to broaden financial inclusion for the unbanked population by providing
a positive and safe borrowing experience. The truth is, many people, including first-time
borrowers and immigrants, struggle to get loans due to insufficient or non-existent credit
history. In order to make sure this underserved population has a positive loan experience;
Home Credit makes use of a variety of alternative data - including telco and transactional
information - to predict their clients' repayment abilities.

### c) Decisions of interest:
The key decisions we want to make from our analysis of the data are as follows:

1. Which loan applications do we accept?
2. How much loan do we give to an applicant?
3. What demographics do we target our marketing at?

### d) Decision makers:
| Decision of Interest | Decision Maker(s) |
| -- | -- |
| Which loan applications do we accept? | Branch Manager, Credit Risk Manager & Loan Underwriter |
| How much loan do we give to an applicant? | Branch Manager |
| What demographics do we target our marketing at? | Marketing Manager |

<a id='busund'></a>
## BUSINESS UNDERSTANDING

### a) Business objective:
To determine the loan eligibility of people with insufficient or non-existent credit history using
financial and non-financial indicators, such as income, age and education.

### b) Situation assessment:
Generally, banks and other financial institutions review a person’s credit history to figure out
his/her loan repayment ability. Based on such a review, they decide on whether to sanction
a loan. Many financial institutions do not consider customers without enough credit history
even if they can repay their loans. This unserved portion of the population presents a business
opportunity. A model will enable us to expand our business by identifying the profitable 
members of this unbanked population.

### c) Data mining goals:
Through Clustering, Classification and Regression, we aim to identify the predictors of loan
default, and build models to decide if the loan should be sanctioned and how much should be
sanctioned. This would involve:

1. Identifying patterns in the dataset and analyse the factors that give an insight on the
borrower’s inability to pay their instalments on time.
2. Classifying borrowers into different categories based on their income, age, education
and other features.
3. Determining the amount of loan to be sanctioned based on the client’s repayment
capacity.

<a id='dataund'></a>
## DATA UNDERSTANDING

### a) Data requirements:
To assess a borrower’s capability and disposition towards loan repayment, we would need to
examine several financial and non-financial factors. Credit worthiness of a client can be
assessed using the industry-wide accepted “5 C’s”. The data required for this purpose may
include:
* ***Capacity***: The financial/earning capacity of the borrower, identifying factors such as income
(allowances, type of occupation, commission), debt to income ratio (should not exceed 43%).
* ***Capital***: The savings, equity and other investments of the customer, as well as evidence of
money in account for more than 90 days.
* ***Collateral***: Security (type of security), cost of money borrowed, ownership of property etc.
* ***Conditions***: Type of loan/credit, Loan to Value Ratio, age of the customer and Loan Annuity
relative to it.
* ***Character***: History of late payments/default, and work history/background. The latter is
used to determine employment stability – applicants who change jobs frequently or are self-
employed pose a bigger risk for us.

### b) Describe data:
We selected the following 19 out of 102 variables based on the above principles, through the
removal of empty observations and multicollinearity:

|Variables|Description|
|:----|:----|
|AMT_CREDIT| Credit amount of the loan|
|CNT_CHILDREN| Number of children the client has|
|NAME_FAMILY_STATUS| Family status of the client (Single| Married etc.)|
|AMT_INCOME_TOTAL| Income of the client|
|CODE_GENDER| Gender of the client|
|DAYS_BIRTH| Client's age in days at the time of application|
|DAYS_EMPLOYED| Number of days before the application the client started current employment|
|FLAG_PHONE| Did client provide home phone (1=YES| 0=NO)|
|NAME_EDUCATION_TYPE| Level of highest education the client achieved|
|7EXT_SOURCE_2| Normalized score from external data source (Source 2)|
|EXT_SOURCE_3| Normalized score from external data source (Source 3)|
|REGION_POPULATION_RELATIVE| Normalized population of region where client lives|
|FLAG_OWN_CAR| Flag if the client owns a car (1=YES| 0=NO)|
|AMT_REQ_CREDIT_BUREAU_YEAR| Number of enquiries to Credit Bureau about the client one day year (excluding last 3 months before application)|
|OCCUPATION_TYPE| Occupation of the client|
|REG_CITY_NOT_LIVE_CITY| Flag if client's permanent address does not match contact address (1=different| 0=same| at city level)|
|REGION_RATING_CLIENT| Our rating of the region where client lives (1|2|3)|
|OBS_30_CNT_SOCIAL_CIRCLE| How many observations of client's social surroundings with observable 30 DPD (days past due) default|
|TARGET| Target variable (1 - client with payment difficulties: he/she had late payment more than X days on at least one of the first Y instalments of the loan in our sample| 0 - all other cases)|

### c) Sources:
The data consists of:

1. Internal Data generated by Home Credit
2.  Data obtained from the Credit Bureau

We have obtained these datasets through Kaggle (https://www.kaggle.com/c/home-credit-default-risk/overview).

### d) Quality:
1. Accuracy – Kaggle screens all their datasets before posting them and as such, there
should not be any error that significantly affects our analysis. However, we will scan
for anomalies before starting our analysis.
2. Accessibility – The dataset’s terms of use allow academic research and education. Our
use is in conformity with those terms.
3. Comprehensiveness – All required data within the entire scope of our work is collected
and enough for our analysis.
4. Consistency – Data is reliable, homogeneous, and replicable by different users.
5. Currency – Since the data relates to past transactions, it is unlikely to change.
6. Definition – All variables under consideration are well-defined and unambiguous.
7. Relevancy – Data consists of factors which affect borrowings, and hence, is relevant
for our purpose.
8. Timeliness – Data was already available in the public domain (on Kaggle).
