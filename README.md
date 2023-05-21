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
  This took a while to run but resulted 
  
