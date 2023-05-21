# 449-Project
project449 code

  The data set that I found was from the kaggle website. The data itself came from a ongoing study in Framingham, Massachusetts. 
The data set has 4000 observations and 15 variables including one being heart disease diagnosis within the last 10 years. 
There was one slight issue while dealing with the data and that was that the data was not balanced with there being only 100 
observations with heart disease being diagnosed compared ot the 3500 that were not. I re-sampled the data by oversampling, 
but only resampled after making the split on training and testing data. 

 The goal of this project was to design a logistic regression model that would accurately predict the diaganosis of a patient
developing heart diseasse. There were 15 different variables that were included in the data set and those were sex(male/female),
age, education, current smoker, cigs per day, blood preassure medicine, if they've had a stroke, if they have hypertension, diabetes,
cholestoral levels, Systolic and diastolic blood pressure, and glucose level. The data set had one variable that needed to be turned
into a factor and that was eduacation level. Other than that evey other categorical variable was binary so R was able to adress them 
handily. The data set also had many a few data points with missing variables which were removed from the data set. 

   When designing the model I first started with creating the saturated model and running a few tests on it. Since this is a 
  binomial predictor problem I compared the models AIC's to eachother as well as looked as residual deviances. The saturated model 
  Had an AIC of ~4800 and a residual deviance of 4000. From there, I ran a best subset algorithim to find the best subset of predictors.
  This took a while to run but resulted in a model with 11 predictors compared to the 14 that the saturated model had. Those were sex, age education, cigs per day, blood preassure meds, diabetes, cholestoral systolic and diastolic blood preassure and glucose. This model had a reduced AIC at ~4700 and a residual deviance of around 4000. 
  
   When looking at the model the next goal is to find the best cut off point for the prediction values. When creating the model logistic regression produces the log odds of the outcome. In each case it's good to pick a cut off point for if a input will be labled a "success" or a "failure, in my case heart disease or no heart disease. The best way to determin this is through the creation of a ROC curve.
When looking at the ROC curve of the model I found that the best cut off point was .5. For predicitng heart disease it may be valuable to move the cut off point slightly lower, as while it would create more false positives, it does improve the accurcy of making correct heart disease predictions.
Going the otherway it would be worse to increase the cut off point as it would create false negative that could endanger patients. The risk of a false negative is much worse than that of a false positive becasue the strategy to avoid heart disease is to maintain health 
and there is usually little downside to that. The ROC curve yeilded a .73 area under the curve. While that is not a super great it's also not a terrible result. The specifictiy and sensetivity were both in the upper 60% rates. This was done on 30% testing values and trained on the other 70%. The next thing that I tested was the link function in the binomial model. That resulted in an almost identical results in AIC and residual deviance. When testing the identity version I ran into issue with setting starting values that we could not fix. 

  From there the model was cross validated in two different ways. The cross validation did not yeild anything very surprising. The average AIC for the best model when using LOOCVed was around 4800 a bit worse than the original model but not by a large amount. Alternatively the average area under the curve for the LOOCVed model was at .73. When working on K-fold cross validation I yeilded simmilar results with AIC on average being around 4800 and the AUC at .73. 
  
  The results that my model yeilded were decent but I feel that there are things from the class 449 that could be implemented to improve or predict differently. Things like random forests or support vector machines could be a very useful strategy for predicting heart disease. Ridge and Lasso regression could also be an easy way to improve the logistic regression modeling that was already done. 
