# Credit Risk - Supervised ML Model Report 

## Overview of the Analysis

The purpose of this analysis is to create a model that predicts if a loan can be correctly categorised as 'healthy' or 'high-risk'. The focus being on the 'high-risk' category in particular. The high-risk category would be the key metric in this context as it is the most beneficial piece of information for the lending organisation. 

The lending data used for this analysis includes: 
- `Loan Size`
- `Interest Rate`
- `Borrower Income`
- `Debt to Income`
- `Number of accounts`
- `Derogatory Marks`
- `Total Debt`
- `Loan Status (Healthy or High-Risk)`

Ultimately we need a model that can accuratly predict which loans are 'high-risk'. 

In our dataset we had a total of:
- *75036 Healthy Loans*
- *2500 High-Risk Loans*

## Overview of the ML process
- Imported CSV file
- Set 'loan_status' as our dependent variable as *'y'*
- Set remaining columns as features represented as *'X'*
- I split the dataset into training and testing data, and used stratify=y to       ensure a representative sample of each class in both the training and test datasets.
- I then implemented a Logistic Regression model from the sklearn module. 
- Using confusion matrix and a classificartion report i could then evaluate the effectiveness of the model. 


## Results
**Model Accuracy, Precision, Recall, and F1 scores:**

    - Overall model accuracy = 99%
    - Healthy Loan precision score = 100%
    - Healthy Loan recall score = 100%
    - Healthy Loan f1-score = 100%
    - High-Risk Loan precision score = 87%
    - High-Risk Loan recall score = 89%
    - High-Risk Loan f1-score score = 88%


Overall the model has a general accuracy of 99%, but given the imbalanced classes within the dataset (75,036 healthy loans vs only 2,500 high-risk loans), lets looks at our specific categories for a deeper understanding of the model...


**Predicting a Healthy Loan:**

The model predicts the 'healthy loan' category with a precision of 100%, meaning that every loan that the model predicted as 'healthy' was indeed a healthy loan. 

The model also had a success rate of 100% in predicting all the *actual* healthy loans in the test data as indicated by the recall score of 1.0. So the model correctly identified all healthy loans from our test data. 


**Predicting a High-Risk Loan:**

Given the context of the data, the real metric we are interested in is predicting credit risk, so this is where the analysis needs to be thorough. In the context of lending, incorrectly classifying a high-risk loan as healthy could result in significant financial losses for the institution. Hence, this category warrants detailed scrutiny.

The model predicts the 'high-risk loan' category with a precision of 87%, meaning that 87% of the loans that the model predicted as high-risk, were in fact high-risk. 

The model correctly predicted the *actual* high-risk loans with a success rate of 89% (as indicated by the recall score of 0.89). This is our most important metric for this case. 

<span style="color:red">**This means that the model missed 11% of high-risk loans. From our test data, this equates to *67 missed high-risk loans out of a total 625 high-risk loans* **</span>


An F1-score of 88% for the high-risk loan category means that the model has a balanced performance in terms of both false positives and false negatives for this category.

## Conclusion/Recommendation:

Given the recall of `89%` for high-risk loans, this model seems effective in identifying a majority of potential credit risks and as such, I would recommend the model.  However, as with all models, continual monitoring and adjustment might be needed to ensure its performance over time
