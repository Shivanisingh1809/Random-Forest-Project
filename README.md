# Random-Forest-Project
This repository stores implementation to Decision Trees and Random Forest 



Decision trees and random forests are supervised learning algorithms used for both classification and regression problems. These two algorithms are best explained together because random forests are a bunch of decision trees combined. There are ofcourse certain dynamics and parameters to consider when creating and combining decision trees.


A decision tree builds upon iteratively asking questions to partition data. Our aim is to increase the predictiveness of the model as much as possible at each partitioning so that the model keeps gaining information about the dataset. Randomly splitting the features does not usually give us valuable insight about the dataset. Splits that increase purity of nodes are more informative. The purity of a node is inversely proportional to the distribution of different classes in that node. 

There are two ways to measure the quality of a split: Gini Impurity and Entropy. They essentially measure the impurity and give similar results. Scikit-learn uses gini index by default but you can change it to entropy using criterion parameter.
Gini impurity is a measure of how often a randomly chosen element from the set would be incorrectly labeled if it was randomly labeled according to the distribution of labels in the subset
Entropy is a measure of uncertainty or randomness. The more randomness a variable has, the higher the entropy is. The variables with uniform distribution have the highest entropy.



Random Forests
Random forest is an ensemble of many decision trees. Random forests are built using a method called bagging in which each decision trees are used as parallel estimators. If used for a classification problem, the result is based on majority vote of the results received from each decision tree. For regression, the prediction of a leaf node is the mean value of the target values in that leaf. Random forest regression takes mean value of the results from decision trees.

Random forests reduce the risk of overfitting and accuracy is much higher than a single decision tree. Furthermore, decision trees in a random forest run in parallel so that the time does not become a bottleneck.

The success of a random forest highly depends on using uncorrelated decision trees. If we use same or very similar trees, overall result will not be much different than the result of a single decision tree. Random forests achieve to have uncorrelated decision trees by bootstrapping and feature randomness.




                  For this project I will be exploring publicly available data from LendingClub.com. Lending Club connects people who need money (borrowers) with                     people who have money (investors). Hopefully, as an investor you would want to invest in people who showed a profile of having a high probability of                      paying you back. We will try to create a model that will help predict this.

          Lending club had a very interesting year in 2016, so let's check out some of their data and keep the context in mind. This data is from before they even went         public.

          We will use lending data from 2007-2010 and be trying to classify and predict whether or not the borrower paid back their loan in full. You can download the        data from here or just use the csv already provided. It's recommended you use the csv provided as it has been cleaned of NA values.

          Here are what the columns represent:

         1. credit.policy: 1 if the customer meets the credit underwriting criteria of LendingClub.com, and 0 otherwise.
         2. purpose: The purpose of the loan (takes values "credit_card", "debt_consolidation", "educational", "major_purchase", "small_business", and "all_other").
         3. int.rate: The interest rate of the loan, as a proportion (a rate of 11% would be stored as 0.11). Borrowers judged by LendingClub.com to be more risky are                        assigned higher interest rates.
         4.installment: The monthly installments owed by the borrower if the loan is funded.
         5. log.annual.inc: The natural log of the self-reported annual income of the borrower.
         6. dti: The debt-to-income ratio of the borrower (amount of debt divided by annual income).
         7.fico: The FICO credit score of the borrower.
         8. days.with.cr.line: The number of days the borrower has had a credit line.
         9. revol.bal: The borrower's revolving balance (amount unpaid at the end of the credit card billing cycle).
         10. revol.util: The borrower's revolving line utilization rate (the amount of the credit line used relative to total credit available).
         11. inq.last.6mths: The borrower's number of inquiries by creditors in the last 6 months.
         12. delinq.2yrs: The number of times the borrower had been 30+ days past due on a payment in the past 2 years.
         13. pub.rec: The borrower's number of derogatory public records (bankruptcy filings, tax liens, or judgments).
