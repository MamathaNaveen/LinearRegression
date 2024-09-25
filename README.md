Problem Statement

A bike-sharing system is a service in which bikes are made available for shared use to individuals on a short term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system.

A US bike-sharing provider BoomBikes has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state.

They have contracted a consulting company to understand the factors on which the demand for these shared bikes depends. Specifically, they want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to know:

Which variables are significant in predicting the demand for shared bikes. How well those variables describe the bike demands

Business Goal

We are required to model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market.


## Table of Contents
* [General Info](#general-information)
  
  
* [Technologies Used](#technologies-used)
  
* [Conclusions](#conclusions)
  
Observations from Pariplot

Variables Temp and Atemp is linear/colinear
Variable Cnt increase with increase in temp,atemp variables.
Less bookings seen with Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds
Less booking seen when holiday is 1
Booking count seen increase in 2019 when compared to 2018.

Bivariate Analysis Observations

2019 increase in number of bookings cnt compared for 2018.
Less booking seen with Weathersit-3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds. Highest bookings seen in Weathersit_1 ie. Clear, Few clouds, Partly cloudy, Partly cloudy
Gradual increase in bookings seen in 2nd and 3rd quarter for both years.
HIghest bookings seen when there is Holiday(0) with median lying 4800.

Conclusions: 
From Manual Statsmodel built, Multiple Linear Regression Model:
**r2_score calculations...**
- **R2 square of Train model = 84.1%**
- **R2_score of Test model = 80.3%**
  OLS Regression Results
  Dep. Variable: cnt R-squared: 0.841
  Model: OLS Adj. R-squared: 0.837
  Method: Least Squares F-statistic: 201.7
  Date: Tue, 24 Sep 2024 Prob (F-statistic): 2.01e-188
  Time: 12:39:43 Log-Likelihood: -4118.0
  No. Observations: 510 AIC: 8264.
  Df Residuals: 496 BIC: 8323.
  Df Model: 13
  Covariance Type: nonrobust
  
- **Final Model build**
    cnt = sun*502.5 + oct*298.1 + yr*2025.8 + holiday*-470.38 + workingday*411.19 + temp*4439 + windspeed*-1330.3 + summer*885.75 + winter*1100.9 + Aug*468.8 + sept*1029.96

  **Using RFE for automated feature selection**
  Steps:
    Importing data, Data exploration, Data Cleanup.
    Generating Categorical variables.
    Creating dummy variables.
    Scaling Numerical values using Min-Max Scaler.
    BUilding Model using RFE. (Feature selection step=10)
    Including Statsmodel suggestions if required to improve R2 value is required.
  Adding new features based on previous insights from Manual Statmodel approach

Since we have manually built model with R2=84% covered , I have picked few features('yr','winter','weathersit_3') with increased co-efficent to below set and compared R2 again. We can see that R2 have now increased from 46% to 78%. We will retain this as final model for further testing.
Now we will remove Nov and Oct step by Step since the p-value was 0.99 and 0.72
Final List of features (9 selected ): ['holiday','atemp', 'windspeed', 'April','July', 'Sept', 'winter','yr','weathersit_3']
Final R2 value is 78.8%
Final Adj. R-squared: 78.3%
Final VIF values also looks good. Features VIF
1 atemp 4.12
2 windspeed 3.03
7 yr 2.01
4 July 1.34
6 winter 1.32
5 Sept 1.20
3 April 1.17
8 weathersit_3 1.06
0 holiday 1.03

  We have successfully build both models which covers ~80% determines the variance in the dependent variable that can be explained by the independent variable.

  
Technologies Used

Python - version 3.11.1

Python Numpy - version 1.26.4

Python Pandas - version 2.1.4

Python Matplotlib - version 3.7.3

Python Seaborn - version 0.12.2

Python Statsmodel

Python Sklearn.

Contact
Created by @MamathaNaveen - feel free to contact us!
