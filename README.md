
#####HIV Regression Case Study


Using the merged HIV models. We wanted to find out with combination of predictors (X) created the best prediction of out target (Y). In our case we want to compare OLS regression against Ridge Regression and Lasso Regression to see which model return the lowest Mean Squared Error. 

Then we will take the best model and features to fit our new regression line.


**1) We took in the merged Data frames and dropped the na values.**

**2) During our EDA we looked at the The initial  Pearson correlations between the features as it related to our target variable  “HIVincidence” (#of cases / population). ** 

We found the following columns had Pearson correlations above .25.:

**HIV drag, HIV inched  MH_fac      Med_mh_Fac.  Med_sa_fac    Med SMAT _fac.   TMAT.    Plhiv.  SmATred_fac          Tmat_fa              bup_phys.         %msm12month           %msm5ye**    




**3) Our next step was to Train-Test-Split our data and set up our method of cross validation and set our Test Data validation to .25.**


**4) We fit Ridge regression, leaving out Geographic data columns that were nonsensical to the tests we were running. **


**5) We wrote a function to find the Mean Squared error of our Ridge Regression on our Test and predicted Y values: **

  We found the Mean Squared Error with an alpha (lambda) at .05 to be **20317.47**.


**6) In a 10 fold cross validation function we estimated the error of the model using our Ridge Regression:**

Our Mean Training Cross Validation error is **.38**
And our Test cross validation error is **.87**



 
**7) Then we  performed cross validation on different values of alpha.**




**8)  We found the optimal alpha on the for the mean cross validation errors test. 
Then plotted the Ridge Regression Train and Test Mean Squared error. With Mean Squared Error as Mean Squared Error on the Y-axis and the log of alphas on the X-axis**



**9) We took the individual coefficient paths and plotted them against alphas.**

![alt text](https://github.com/kyle-black/regression_case_study/blob/main/images/ridge_regression_standard_coefficient_paths.png)


**10)
