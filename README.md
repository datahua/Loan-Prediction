![Vehicle Loan Default Prediction](/dataset-cover.png)
## Loan-Prediction

##### please read the pdf file, as jupter notebook file did not get rendered in github server due to limited computation power.


Data description:
  - 42.98 MB 
  - with 41 columns and 233,154 rows
  - response variable: Loan_default, binary outcome with Yes and No
  - predictor variable: 1 index variable, 39 descriptive variables including 
      1. Loanee Information (Demographic data like age, income, Identity proof etc.) 
      2. Loan Information (Disbursal details, amount, EMI, loan to value ratio etc.) 
      3. Bureau data & history (Bureau score, number of active accounts, the status of other loans, credit history etc.)
  
  
Purpose of this project for me is to implement the hyperparamters tuning, and different resampling techniques to get higher predictive accuracy, especially the predictive accuracy of event loan default (True Positive). The final accuracy achieved 85%, higher than the highest acc other users acheieved on kaggle (78%). Sample EDA work of mine can be read on [Here.](https://github.com/datahua/EDA-Visualziation-Text-Mining-with_R/blob/main/EDA%2BVisualziation%2BText%20Mining_R.pdf)

**Good stuff I did with the project**
1. use *datatable* to fast load the dataset in only 3 sec
2. Performed data standardization to ensure the internal consistency of entire dataset.
3. Selected important 23 features out of 53, using their correlation along with the Boruta feature selection algorithm. It was slow when catboost model not being implemented. (I left my PC on for the entire night, the progress was still 0%. (default model was random forest) After I implemented catboost model, it only took 30 minutes.)
4. set logistic linear regression as baseline model, however, the predictive accuracy is poor and unsymmetrical, (0% accuracy at predicting True positive due to extremely skewed class distribution)
5. using oversampling techniques SMOTE(Synthetic Minority Oversampling Technique), ADASYN(Adaptive Synthetic algorithm) to balance the dataset (adding more true positive for learning purpose).
6. using xgboost, random forest, and catboost as classifer models. Compared their predictive performance horizontally.
7. tuned hyperparameter of catboost model, increased the recall rate
8. visualized the importance of features 
9. achieved final acc with untuned catboost model

---
Possible improvement:
1. implementation of k-fold
2. more permutations with hyperparameters
3. implement certain regularization like lasso, ridge
