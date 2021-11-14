# Home Credit Defaul Risk

SUHAIL LALA, OLUWATIMILEHIN “SAM” THOMAS,
ABDULRAHMAN ALRUBAIYA, VENKATA ADITYA IMMANNI

## ACKNOWLEDGEMENT
Our project on HOME CREDIT DEFAULT RISK has been a great learning experience. We were
exposed to a variance of subject matter, concerns and arguments that helped us collectively
assemble and shape the project.
We acknowledge Dr. Prakash Shrivastava under whose guidance we were able to complete
the project and effectively present its valuable benefits.
A greater share of inputs and knowledge from each one of us made this project report
possible to its rightful accuracy.
To all our colleagues who have helped us either directly or indirectly, we are grateful for their
valuable inputs.

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
