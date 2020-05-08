# COVID19_Forecasting

Appropriate and timely information is the need of the hour to keep people aware of the effect of pandemic COVID-19. To control and prevent the spread of COVID-19 we will develop a system to predict the spread of the disease in future dates. The future predictions in the increase in the number of COVID-19 cases will help the government to take appropriate actions ahead of time.

Here we have used Machine Learning to predict the future values of the number of COVID-19 Cases that might take place in the world and in the country India.

### Requirements:
* Python 3.5 or 3.6+
* numpy  '1.18.2'
* pandas  '0.25.3'
* matplotlib  '3.2.1'
* scikit-learn  '0.19.1'

``` 
pip install numpy
```
```
pip install pandas
```
```
pip install matplotlib
```
```
pip install scikit-learn
```

### Data Collection:
For training the model, the datasets have been taken from two sources.
#### 1. Dataset for World Prediction
The dataset is taken from [CSSEGISandData, John Hopkins University](https://github.com/CSSEGISandData/COVID-19/tree/master/csse_covid_19_data/csse_covid_19_time_series), that is the time series data collected for the COVID-19 cases since 22 January, 2020.
This source provides us with separate time series data for Confirmed, Recovered and Deceased Cases of COVID-19 globally. The data is updated daily.
#### 2. Dataset for India Prediction
The dataset is taken from [COVID19 India Org](https://api.covid19india.org/csv/latest/state_wise_daily.csv) (This link will download the csv file for India's State-wise Details of Cases).
This source provides time series data for Confirmed, Recovered and Deceased Cases of COVID-19 in India with the count of cases for each state. 
##### Note: We have modified the dataset according to the requirements for getting best results. The dataset has been divided into 3 parts for each case as confirmed, recovered and deceased and further calculated the cumulative values for each state.

#### Original Dataset
![](https://github.com/CodensureLetsCode/COVID19_Forecasting/blob/master/images/indiaOrgData.png?raw=true)

#### Modified Datasets
India Confirmed Cases
![IndiaConfirmedCases](https://github.com/CodensureLetsCode/COVID19_Forecasting/blob/master/images/indiaConfirmed.png?raw=true)

India Recovered Cases
![IndiaRecoveredCases](https://github.com/CodensureLetsCode/COVID19_Forecasting/blob/master/images/indiaRecovered.png?raw=true)

India Deceased Cases
![IndiaDeceasedCases](https://github.com/CodensureLetsCode/COVID19_Forecasting/blob/master/images/indiaDeaths.png?raw=true)

### Model Creation and Evaluation
The forecasting model is made using SVR - Support Vector Regression which is a Machine Learning based Regression Technique. This is suitable for non-linear regression problem similar to the spread of COVID-19 disease. SVR uses SVM (Support Vector Machine), which is a classification algorithm, for predicting a continuous variable.
Here, this will be predicting the number of cases of COVID-19. 
The best parameters for SVR model, which are 'kernel', 'C', 'gamma', 'epsilon' and 'shrinking' are selected and applied for making better predictions.
The model is evaluated using MAE (Mean Absolute Error) and MSE (Mean Squared Error).

The model predicts the future number of cases for the next 10 days. The Actual Confirmed Cases till 6 May, 2020 and the Predictions for the next 10 days in India can be seen in the plot given below,

![Predictions](https://github.com/CodensureLetsCode/COVID19_Forecasting/blob/master/images/India_Predictions.png?raw=true)

The predictions are shown for the future dates:
##### 05/07/2020 -> 56884.07268483646
##### 05/08/2020 -> 60091.46559190028
##### 05/09/2020 -> 63417.637497878924
##### 05/10/2020 -> 66864.7480209347
##### 05/11/2020 -> 70434.95677922937
##### 05/12/2020 -> 74130.4233909254
##### 05/13/2020 -> 77953.30747418455
##### 05/14/2020 -> 81905.7686471696
##### 05/15/2020 -> 85989.96652804167
##### 05/16/2020 -> 90208.06073496336

These predictions can be improved with further training and evaluation. 

### Future Additions to the System
This project is under development. Here, we aim to make a system which covers every aspect that can cause increase or decrease in the number of cases. Thus, we will also be considering the following factors for making more realistic and acceptable forecasting of the spread of COVID-19.
Factors to be considered:
1. COVID-19 Cases (SVR Predictions)
2. Weather Data
3. Social Data (Twitter)
4. News Updates
5. Demographics

#### WEATHER DATA
The weather data for India will be retrieved from meteoblue meteorological service and it will include the hourly details of the Temperature (°C) and Humidity (%) of the country. The mean values of both Temperature and Humidity will be used for making predictions that how changes in weather will affect the spread of COVID-19.

#### SOCIAL DATA
The social dataset of Twitter will be used for extracting data about the cases of the COVID-19 using Natural Language Processing (NLP). People may post details of the newly tested positive cases which can be very useful for making predictions for early detection of the disease.  

#### NEWS UPDATES
There is a sudden increase in the events taking place all over the country due to the panic created by COVID-19. These events may include any social or political gathering, making goods available to the public in some areas, large migrations of people, etc. These events can cause an increase in the number of interactions among people and can lead to the spread of the disease at a much faster pace. These events are mostly updated very frequently on news sites. The trusted news sites can be used to extract information from future events and make predictions about the increase in transmission of the disease. This feature can add more weightage to the predicted number of confirmed cases for future dates. 
Examples of the events in case of COVID-19 can be: 
* Violation of Lockdown
* Social Gathering
* Difficulties to Hospitals in giving treatment
* Indian Markets Functioning 

#### DEMOGRAPHICS
The Indian Population Demographics will be considered once we have the predictions and based on this a sequence of data will be generated. The Machine Learning approach of Sequence Classification will be applied to classify the level of severity of the future number of cases based on the demographics. For this, we will be requiring patient data for the population of each state from the Indian government and hospitals. From the dataset provided by the hospitals and government, we can keep a track of different sectors of the population that are affected by COVID-19 and how much percent of the population is suspected to be affected and under home quarantine and the percent which are safe and healthy. 

The entire approach to the solution can be represented as shown in the diagram below,
![ApproachDiagram](https://github.com/CodensureLetsCode/COVID19_Forecasting/blob/master/images/Approach%20Diagram.png?raw=true)

### References:
1. https://www.researchgate.net/publication/224408260_Time_Series_Prediction_Using_Support_Vector_Machines_A_Survey
2. https://api.covid19india.org/csv/
3. https://github.com/CSSEGISandData/COVID-19


#### Team Members:
##### Aditi Sharma
##### Himanshu Sen
##### Jay Sharma
