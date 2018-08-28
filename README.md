# Logistic Regression in AzureML
<b>Summary:</b> In this experiment, we will build a machine learning model that will predict for an inmate that if he will commit crime when released on parole. <i>This experiment was built in April 2015.</i>

AzureML Gallery: https://gallery.azureml.net/Details/eae76138f1f84dfeb7bfb6e9ea7dfa26

### Description: 
Parole board in Criminal Justice System, analyze an inmate's application (along with behavior, history etc) and decide to release an inmate on parole or deny the application. This type of model can be very helpful for the parole board. 

The dataset used in this experiment is taken from [15.071x The Analytics Edge](https://www.edx.org/course/v2/analytics-edge-mitx-15-071x-0 ), an online course taught by MIT in 2015, which is a subset of the data provided by National Corrections Reporting Program. This model uses Logistic Regression (also known as Logit Regression) for prediction. We will try to predict "violator" column's value which can be 1 (if parolee violated the parole) or 0 (if parolee did not committed any crime while on parole). Since the outcome of our predictive model is either 0 or 1 we can apply "Two-Class Logistic Regression" algorithm to our dataset. 

### Dataset:
<b>male:</b> 1 if the parolee is male, 0 if female<br>
<b>race:</b> 1 if the parolee is white, 2 otherwise<br>
<b>age:</b> the parolee's age (in years) when he or she was released from prison<br>
<b>state:</b> a code for the parolee's state. 2 is Kentucky, 3 is Louisiana, 4 is Virginia, and 1 is any other state.<br>
<b>time.served:</b> the number of months the parolee served in prison (limited by the inclusion criteria to not exceed 6 months).<br>
<b>max.sentence:</b> the maximum sentence length for all charges, in months (limited by the inclusion criteria to not exceed 18 months).<br>
<b>multiple.offenses:</b> 1 if the parolee was incarcerated for multiple offenses, 0 otherwise.<br> 
<b>crime:</b> 2 is larceny, 3 is drug-related crime, 4 is driving-related crime, and 1 is any other crime.<br>
<b>violator:</b> 1 if the parolee violated the parole, and 0 if the parolee completed the parole without violation.<br>

<img src="https://github.com/AlgoNinja/LogisticReg-AzureML/blob/master/images/AzureML.png">

### Steps:
1. Drag the parole.csv from Saved Datasets. 
2. Split the datset into 70% Training data and 30% Test data. Make the random seed to 144.
3. Fill the 70% training data into Train Model and select the column "violator" as we are trying to predict this column's outcome.
4. Select "Two-Class Logistic Regression" from Machine Learning section and apply it to the Training Model. Leave default values as it is.
5. Connect the outcome of the Train Model to the Score Model that also takes 30% of the test data to apply the algorithm.
6. Lastly we have to evaluate the Score Model using Evaluate Model to determine the accuracy of our model.
7. Select Visualize from the output node of the Train Model and you will see the Accuracy of this model is determined as 0.906 which is pretty awesome. Remember perfect accuracy is 1. Area Under the Curve (AUC) has been calculated as 0.882 (with 0.5 threshold value) which also shows that this is a pretty strong model for parole prediction. 

Ref: http://www.icpsr.umich.edu/icpsrweb/NACJD/series/38/studies/26521?archive=NACJD&sortBy=7
