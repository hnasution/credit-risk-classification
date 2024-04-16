# Module 20 Supervised Learning

## credit-risk-classification

### Background
In this Challenge, you’ll use various techniques to train and evaluate a model based on loan risk. You’ll use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

### Instructions
The instructions for this Challenge are divided into the following subsections:

* Split the Data into Training and Testing Sets
* Create a Logistic Regression Model with the Original Data
* Write a Credit Risk Analysis Report

### Split the Data into Training and Testing Sets
Open the starter code notebook and use it to complete the following steps:

1. Read the lending_data.csv data from the Resources folder into a Pandas DataFrame.
2. Create the labels set (y) from the “loan_status” column, and then create the features (X) DataFrame from the remaining columns

### NOTE
A value of 0 in the “loan_status” column means that the loan is healthy. A value of 1 means that the loan has a high risk of defaulting.

3. Split the data into training and testing datasets by using train_test_split.

### Create a Logistic Regression Model with the Original Data
Use your knowledge of logistic regression to complete the following steps:

1. Fit a logistic regression model by using the training data (X_train and y_train).
2. Save the predictions for the testing data labels by using the testing feature data (X_test) and the fitted model.
3. Evaluate the model’s performance by doing the following:
    * Generate a confusion matrix.
    * Print the classification report.
4. Answer the following question: How well does the logistic regression model predict both the 0 (healthy loan) and 1 (high-risk loan) labels?

### Write a Credit Risk Analysis Report
Write a brief report that includes a summary and analysis of the performance of the machine learning models that you used in this homework. You should write this report as the README.md file included in your GitHub repository.

Structure your report by using the report template that Starter_Code.zip includes, ensuring that it contains the following:

1. An overview of the analysis: Explain the purpose of this analysis.
    This analysis aims to build a system that can guess how likely someone is to repay a loan on a peer-to-peer lending platform. 
    The system will be tested to see how good it is at making these predictions.

2. The results: Using a bulleted list, describe the accuracy score, the precision score, and recall score of the machine learning model.

    #### Results:      
    * Precision Score 
        - Precision (Class 0 - Healthy Loan): 1.00
        This means out of all the loans the model predicted as Healthy (Class 0), 100% were actually Healthy Loans. In other words, the model perfectly identified all the healthy loans it predicted.

        - Precision (Class 1 - High-Risk Loan): 0.85
        This means out of all the loans the model predicted as High-Risk (Class 1), 85% were actually High-Risk Loans. There's a 15% chance the model might have incorrectly classified a loan as High-Risk when it was actually healthy.

    * Recall Score 
        - Recall (Class 0 - Healthy Loan): 0.99
        This means out of all the actual Healthy Loans in the data, the model identified 99% of them as Healthy. The model might have missed a very small percentage of healthy loans.
    
        - Recall (Class 1 - High-Risk Loan): 0.91
        This means out of all the actual High-Risk Loans in the data, the model identified 91% of them correctly. The model might have missed a small percentage (9%) of the actual high-risk loans.

    The model performs exceptionally well in identifying Healthy Loans (both precision and recall are very high). However, for High-Risk Loans, there's a slightly higher chance of the model misclassifying a loan (lower precision) or missing some high-risk loans entirely (lower recall).

3. A summary: Summarise the results from the machine learning model. Include your justification for recommending the model for use by the company. If you don’t recommend the model, justify your reasoning.
    - The model excels at identifying Healthy Loans (Class 0) with a perfect precision score (1.00) and a near-perfect recall score (0.99). This indicates the model accurately flags good borrowers with minimal misses
    - While recall for High-Risk Loans (Class 1) is good (0.91), precision is lower (0.85). This means there's a higher chance of the model incorrectly classifying some loans as high-risk (false positives) and potentially missing some true high-risk loans (false negatives).
    
    Given the model's exceptional performance in identifying good borrowers, it has the potential to be valuable. However, due to the higher chance of misclassifying high-risk loans, further analysis is recommended before full deployment:
    - Ensure the training data doesn't contain biases that could lead to unfair rejections of good borrowers or underestimating high-risk borrowers.
    - While the results are promising, understanding why the model makes specific predictions (explainability) is crucial. This can help identify potential issues and build trust with lenders using the model.

    