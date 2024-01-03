# Predicting Floods - Time Series Analysis
![image](https://cdni0.trtworld.com/w960/h540/q75/60938_INDarchiveweatherclimateafp_1565768717964.jpg)
![Photo](https://india.mongabay.com/2021/11/freely-available-geospatial-dataset-to-make-flood-research-easier/)


## Business Problem
Floods rank among the most destructive natural calamities, and India faces a substantial impact due to the increasing frequency and severity of floods. This leads to tragic consequences, with certain regions experiencing more pronounced damage, contributing to the loss of lives and livelihoods.
## Data Understanding
The data was taken from MongoBay- Freely available spatial dataset to make Flood Research easier. The data was filtered by major causes of floods. The top 2 causes of Floods were ranked by the number of humans diplaced. Duplicates were removed. For time series analysis, the dates were all converted to datetime, and the dataset is furthur filtered by Year after 2000.  Addionally, all the
null values were replaced by placeholder values of 'Unknown'.

## Data Analysis 

### Exploratory Data Analysis:
#### Humans are Displaced more due to Monsoonal Rains
![image](https://github.com/myt-hue/Flood-Prediction/assets/73657823/1cf9edf3-5923-4df6-895e-85de3c31887d)

#### Flood Status in India
![image](https://github.com/myt-hue/Flood-Prediction/assets/73657823/d2041016-56ef-4f30-99b8-b4496b2bfbf6)

#### Monsoonal Rains affect Coastal Regions
![image](https://github.com/myt-hue/Flood-Prediction/assets/73657823/b7083119-f186-4049-a87f-187495a979f9)

### Modelling
'Area Affected'  was used as the y variable for Time Series Analysis as it showed a yearly trend. Furthur, the data was resampled monthly to reduce noise in data. An Exponenetial Moving Average
(EMA) was applied to smoothen the data (make it more stationary) and apply weight on more recent data points. 

#### Naive Model 
![image](https://github.com/myt-hue/Flood-Prediction/assets/73657823/5f17b2fb-ba5e-41c7-a7f8-2b87288abff9)
RMSE: 58793 

#### ARIMA Model 
RMSE: 55214 
AIC: 3878

#### Random Walk Model
RMSE: 58680
AIC: 3895
The ARIMA model was chosen because it had a better AIC and RMSE value.

#### Autocorrelation Plot
![image](https://github.com/myt-hue/Flood-Prediction/assets/73657823/3e83c74f-4ad6-48eb-a778-29249f85600b)
ACF is consistent throughout multiple lags indicating the present values are strongly correlated with the past values


### Seasonality Decompostion
![image](https://github.com/myt-hue/Flood-Prediction/assets/73657823/2cbf00e3-3d84-4ce1-8cb4-40ea81aa6787)
After perfoming seasonality decomposition, January is the most frequent month for floods to occur


## Future Insights
 1. Perform Logistic Regression to predict Flood Severity
 2. Local Government should  look into different types of Flood Reservoirs/Basins to capture excess water
 3. Local Government should invest in better infrastructure for districts/villages more prone to floods

## For more information
Data taken from https://india.mongabay.com/2021/11/freely-available-geospatial-dataset-to-make-flood-research-easier/

## Repository Structure

You are currently in the README.md file. The 'index.ipynb' file contains the jupyter notebook of the explaratory analysis of the given data that provides step-by-step guide to how we came to our conclusion. 'Images' file contains the images used in this file. The images were taken from the internet.

```
├── Data                             <- Data file used in this project
├── Image                            <- Images and Graphs used in this project obtained from external and internal source
├── .gitignore                       <- Contains list of files to be ignored from GitHub
├── presentation.pdf   <- Slide Presentation of the project
├── README.md                        <- Contains README file to be reviewed    
└── index.ipynb                      <- Jupyter notebook of the project containing codes and analysis


































