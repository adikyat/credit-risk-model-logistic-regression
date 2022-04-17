# credit-risk-model-logistic-regression
My contribution :- I have implemented and understood the concepts of credit risk modelling through the following course - https://www.udemy.com/course/credit-risk-modeling-in-python/ . This project has no novelty , it is a hands-on project to practically understand the concepts. Code's owner rights are with the course instructor.

- Credit risk models predict the likelihood of a customer to miss the loan repayments. They assess the repayment behaviour of an individual depending on the customer's credit history.

#### Step by step process of building a credit risk model :- 
1. Source Data :Bureau, Bank Transactions, Entered Information in XML/JSON format
2. Data Parsing and cleaning
3. PD model: Create dummy variables (one hot) for all required variables and everything should be binary for PD model
4. Calculate WOE for every category in a variable.
5. Calculate Information Value of that variable.
6. Visualize WOE whether it is monotonically inc/dec that shows whether it will help in classification.
7. Group similar sub-groups which make doesn't make a lot change.
8. Group sub-groups having similar and less number of samples/ mix smaller ones with a big one given that WOE should be monotonic.
9. Also convert the continuous variables to discrete dummy variables by binning them using pd.cut method and by checking WOE graph we can decide the bin size.
10. Check IV value(normally should be >=0.02) if the variable is really helpful in classification using that table.
11. Apply logistic regression with p-values model
12. Analyse the coeff,inter,p values and also dump the model. For good, coeff will be more, p-value for all should be <0.05.
13. Analyse ROC-AUC, Gini, Kolmogrov and decide threshold.
14. Calculate scores

#### LGD (Loss given default):- 
1. Here we take only the accounts that were charged-off (written-off)
2. We calculate the dependent variable for the LGD model: recovery rate. It is the ratio of recoveries and funded amount.
3. recovery rates that are greater than 1 to 1 and recovery rates that are less than 0 to 0
4. Do EAD modelling = credit conversion factor - the ratio of the difference of the amount used at the moment of default to the total funded amount
5. Apply Logistic reg and analyse thresholds

#### EAD (Exposure at default):- 
1. Apply linear reg and do validation
2. cal ead and lgd thru ccf and recovery rate.
3. expected loss=ead*lgd*pd
4. sum for all the accounts
5. capital needed to be reserved = el(expected loss)/funded_amt

### Performance of PD (probability of default) model :- 
-** AUC = 68.20% || KS = 27.03%**

- ![image](https://user-images.githubusercontent.com/35119744/163716939-8a2eff7c-0708-4063-b54f-0dd0f3826c55.png)
- ![image](https://user-images.githubusercontent.com/35119744/163716952-8640bf66-b3fa-4fee-89bc-4856485bb816.png)















