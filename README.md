
# HIV Regression Case Study


Using the merged HIV models. We wanted to find out which combination of predictors (X) created the best prediction for our target (Y). In our case we want to compare Linear Regression against Ridge Regression and Lasso Regression to see which model return the lowest Mean Squared Error.  From the best fit regression we will choose the most influential features with help of OLS Regression. 




**1) We took in the merged Data Frames and dropped the nan values.**

**2) During our EDA we looked at the The initial  Pearson correlations between the features as it related to our target variable  “HIVprevalence” (#of cases / population).** 

We found the following columns had Pearson correlations above .25.:

**HIV drag, HIV inched  MH_fac      Med_mh_Fac.  Med_sa_fac    Med SMAT _fac.   TMAT.    Plhiv.  SmATred_fac          Tmat_fa              bup_phys.         %msm12month           %msm5ye**    



 
**3) Our next step was to Train-Test-Split into 75% for training and 25% for testing.**


**4) We fit Ridge Regression, leaving out geographic data columns that were nonsensical to the tests we were running.**


**5) We wrote a function to find the Mean Squared error of our Ridge Regression on our Test values and predicted Y values:**
We found the Mean Squared Error with an alpha (lambda) at .05 to be **20317.47**.




**6) In a 10 fold cross validation function we estimated the error of the model using our Ridge Regression:**

Our Mean Training Cross Validation error is **.38**
And our Test cross validation error is **.87**

It is expected our training error is less than our test error. Since the gap between the errors is large we can expect that we won't be using Ridge Regression.





 
**7) Then we  performed cross validation on different values of alpha. We found the optimal alpha for the mean cross validation.**
alpha = 2950 

![alt test](https://github.com/lraganit-star/regression_case_study/blob/main/images/ridge_regression_train_test_MSE.png)


**8) We took the individual coefficient paths and plotted them against alphas.**

![alt text](https://github.com/kyle-black/regression_case_study/blob/main/images/ridge_regression_standard_coefficient_paths.png)


**9)We repeated the same process, but this time we used Lasso regression.**


![alt text](https://github.com/lraganit-star/regression_case_study/blob/main/images/LASSO_regression_standardized_coefficient_paths_pt2.png)


**11) We found the optimum alpha for the Lasso regression for the Train and Test Mean Squared Error.**

![alt_text](https://github.com/lraganit-star/regression_case_study/blob/main/images/LASSO_regression_train_and_test_MSE.png)

The optimal alpha for the lasso regression is : **0.0009636864286572604**

**12) We compared the RSS for our Ridge, Lasso and Linear Regression:
 
 Final Ridge RSS: 0.633
 
 Final Lasso RSS: 0.516
 
 Final Linear Regression RSS: 0.517**
 
 Lasso has the lowest RSS. So we believe that is our best model.
 
 
 **13) We begin feature engineering on our Lasso model.**
 
 
 
 
 




