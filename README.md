Credit Risk Classification
============================

File Structure
--------------
The repository is organized as follows:
   - credit-risk-classification/Resources/lending_data.csv 
   - credit-risk-classification/Credit_Risk/credit_risk_classification.ipynb 
   - credit-risk-classification/README.txt 


Project Workflow
----------------
1. **Data Loading & Exploration:**  
   - Imported the CSV file (located in the Resources folder) using pandas.
   - Conducted initial exploration with functions like `.head()` and `.value_counts()` to verify the structure and distribution of the data.

2. **Data Preparation:**  
   - Separated the target variable (`loan_status`) from the features, assigning `y` for labels and `X` for predictors.

3. **Data Splitting:**  
   - Divided the data into training and testing sets using an 80/20 split via `train_test_split` (with a fixed random state for reproducibility).

4. **Model Building:**  
   - Configured a Logistic Regression model with an appropriate `random_state` and `max_iter` to ensure convergence.
   - Trained the model using the training set.

5. **Model Evaluation:**  
   - Generated predictions on the testing set.
   - Assessed the model using a confusion matrix and a classification report that detailed accuracy, precision, and recall for both classes.

Analysis/Report

For this project, I worked with a dataset that includes several key financial variables:

  - loan_size
  - interest_rate
  - derogatory_marks
  - total_debt
  - borrower_income
  - debt_to_income
  - num_of_accounts

The target variable, loan_status, tells us if a loan is healthy (0) or high-risk (1). I did a quick dive into the data using commands like .head() and .value_counts() to make sure everything was in order and to see how the labels were distributed.

Here’s how I tackled the problem step by step:

1. **Data Collection & Exploration:**  
   I imported the CSV file from the Resources folder and took a good look at the structure and contents to make sure everything was as expected.

2. **Data Preparation:**  
   I split up the data by separating out the target variable (loan_status) from the rest of the features. This way, `y` represents what I want to predict, and `X` holds all the features.

3. **Data Splitting:**  
   I used train_test_split to break the dataset into training and testing sets with roughly an 80/20 split, using a fixed random state to keep the results reproducible.

4. **Model Building:**  
   I set up a Logistic Regression model. With a specified random_state and a bit of an increase in max_iter to ensure convergence, I trained the model on the training data.

5. **Model Evaluation:**  
   After training, I made predictions with the test set. I then evaluated the model using a confusion matrix and a classification report, which gave me insights into the accuracy, precision, and recall.

I chose Logistic Regression for this task because it’s simple, interpretable, and well-suited for the binary classification of loan statuses.

Results

* **Machine Learning Model 1 (Logistic Regression):**
    * **Accuracy:** I found a 99% accuracy
    * **Precision:** For healthy loans we found 1.0 (100%), for high-risk loans we found 0.86 (86%)
    * **Recall:** For healthy loans we found 1.0 (100%), for high-risk loans we found 0.91 (91%).

The classification report indicated that overall accuracy is near perfect. The model does a great job at predicting healthy loans with precision, but the recall for high-risk loans isn’t as strong, meaning it may be missing some of those high-risk cases.

Summary

**Recommendation:**

- Given its simplicity and transparency, I’d use the logistic regression model as a strong baseline for credit risk assessment.  
- That said, its lower recall on high-risk loans suggests it needs a bit more tuning before you could confidently deploy it in a production setting.  
- To improve, future work could focus on additional feature engineering, tweaking the model (like adjusting class weights), or even trying out other models such as decision trees or ensemble methods to better catch high-risk cases.  
- Remember, the importance of accuracy versus recall depends on the business goal—if flagging high-risk loans is critical, boosting recall might trump overall accuracy.

While logistic regression lays down a good starting point, its current limitations around high-risk prediction mean further refinement would be needed before using it as the sole credit risk assessment tool.

Disclaimer
-------
Code is my own, Microsoft Copilot and Github Copilot were used when necessary to solve for blocks, or debug. Also used for some recommendations when finishing reporting pieces just to ensure readability and presentation. 