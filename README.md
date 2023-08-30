# -ANALYZING-REAL-ESTATE-INVESTMENTS-IN-THE-UNITED-STATES-OF-AMERICA
![Alt Text](https://racing.dronelife.com/wp-content/uploads/2016/06/usa-map.jpg)

# 1.0  Business Understanding

## 1.1 Project Overview

This project explores the world of real estate markets, where prices usually change slowly but can also change drastically due to various factors. The goal is to understand these patterns and factors that influence investment choices. By analyzing data from Zillow Research (found in the Timeseries folder as zillow_data.csv), we want to figure out the top five zip code areas that are the best options for American Properties Corporation to invest in.

## 1.2 Business Problem

**American Properties Corporation (APC),** being a newcomer in the real estate industry wants help in finding the top 5 best zip code areas in the USA, where smart investments can be made. The business challenge at hand is to identify the most promising zip code areas for our stakeholder to invest in real estate. This will involves examining historical housing price data, considering factors like return on investment, region size ranking and property value volatility to uncover patterns, trends, and relationships within the data. The project aims to provide valuable insights that will guide informed investment decisions.

## 1.3 Project Objectives
- To define and identify the criteria that will be used to evaluate the "best" zip codes for investment considering different factors such as ROI, Size ranking of Regions, risks and property value volatility. 
- To identify key patterns, trends and relatioships in the data such as how real estate prices have changed over time. 
- To develop a predictive timeseries model that will forecast return on investment(ROI) of the various Zip codes. 
- To evaluate and select the most appropriate model. 
- To provide recommendations on factors to consider in order invest in property.


# 2.0 Data Understanding
Welcome to our dataset adventure! We're exploring information about home prices over 22 years, from 1996 to 2018. We've got data for 14723 places (zipcodes) and 272 variables. In the first 7 columns, we find details about places and sizes. The other 265 columns are for each month's home prices.
Digging into the heart of our data:
- "SizeRank" shows the average size of places, and it's around 46106.
- The home prices have quite the big range with the the least being about $11,300, and the highest being $3,849,600.
- On average, home prices range from $118,299 to $288,039.
- The way prices jump around is measured by "standard deviation," which goes from $42,500 to $372,054.
- We've got 3 different data types: 219 floats, 49 integers, and 4 objects.
- There is some missing data in the "Metro" and date columns to be dealt with.
- The whole dataset takes up about 30.6 MB.


# 3.0  Data Preparation:
In this stage, data undergoes cleaning and preprocessing to ensure its quality and reliability for subsequent analysis. 

**For data cleaning,** We drop missing values from the categorical column "Metro" but choose not to utilize forward or backward filling techniques on our date columns with missing values in order to prevent any unintended data propagation. We  also drop the redundat "RegionID" column to ensure focus on the important features and  rename "RegionName" to the friendlier "Zipcode" to keep things organized and perform appropriate Data Type conversion to ensure clarity in our analysis.

**For data preprocessing,** We sort things out using the "SizeRank" criterion, pinpointing the top 25% zip codes and then create a new feature "ROI" to help determine how much an investment grows overtime. We also determine the CV to help assess the risk and volatility of the investment.

The ROI and CV collectively helps us rank our "Best 5 Zipcodes" based on their ROIs and risk profiles. These are the places that promise the best returns while keeping things steady and include the ff: **Greenville SC: 29611, Powell OH: 43065, North Decatur, GA: 30033, Corpus Christi, TX: 78414, and Florence SC: 29501.**


# 4.0  Exploratory Data Analysis

## 4.1 Univariate Analysis
In the univariate analysis, we explored state distribution, revealing South Carolina as the major contributor of our best 5 zipcodes. Moreover, we examined the average median house prices by state, with Ohio leading at approximately $350,000 and South Carolina at $120,000. 
![image](https://github.com/ImeldaMasika/Time-Series-Analysis-Zillow-Home-Value-Forecast-Model/assets/128219987/23d16b8e-67a3-453d-b063-39f512e6b281)


## 4.2 Bivariate Analysis
For bivariate analysis, we tracked the average median house price patterns over time, observing a rise until 2008 and a later decline in 2009, followed by a recovery and peak in 2018. We also visualized how ROI varied among cities, with Greenville showing the highest at 1.75, while Florence's ROI stood at 1.65. 
In summary, the EDA uncovered diverse trends within zip codes, ranging from steady growth to fluctuations, showcasing typical market patterns.
![image](https://github.com/ImeldaMasika/Time-Series-Analysis-Zillow-Home-Value-Forecast-Model/assets/128219987/9e53b7dc-c12e-4d78-bd48-37ba8d8a6f38)



# 5.0 Modeling

In the modeling phase, we embarked on a comprehensive journey to develop and refine time series forecasting models for property values across different zip codes. Beginning with baseline ARIMA models, we initially evaluated their performance on both training and test data. These models demonstrated strong predictive abilities with impressively low Mean Squared Error (MSE) values. However, a slight concern emerged as the baseline models exhibited signs of potential overfitting, performing notably better on training data than test data. To address this, we turned to more advanced techniques.

Our exploration led us to a refined ARIMA model and a sophisticated SARIMA model. These models incorporated the seasonal aspect of the data and provided a more intricate understanding of the underlying patterns. The refined ARIMA models demonstrated excellent predictive performance with reduced overfitting tendencies. We then delved into the SARIMA models, which introduced a seasonal component to the forecasting process. These models yielded highly accurate predictions, closely aligning with historical trends. Despite these successes, we aimed to further enhance predictive capabilities and address uncertainty.

The pinnacle of our modeling journey was the implementation of Long Short-Term Memory (LSTM) models with and without Monte Carlo Dropout. These models outshone the previous iterations by capturing intricate patterns and providing insightful uncertainty estimates. Particularly, the LSTM model with Monte Carlo Dropout not only showcased strong predictive power but also offered a more stable and reliable forecast, complete with confidence intervals. With a focus on mitigating overfitting, improving predictive accuracy, and addressing uncertainty, this final model emerges as the optimal choice for forecasting property values across different zip codes, providing valuable insights for investors and stakeholders.

# 6.0 Conclusion
**State-by-State Investment Prospects:** Our analysis reveals distinct investment prospects among states. Ohio stands out with consistently higher property values, offering stable and potentially lucrative investments. In contrast, South Carolina presents a unique opportunity for entry-level investors due to its relatively lower property values.

**Key Metrics for Decision-Making:** ROI emerges as a pivotal metric for evaluating investment potential. Cities like Greenville, Powell, and North Decatur showcase strong ROI figures, indicating efficient investments. Balancing high ROI with lower risk, as indicated by a lower Coefficient of Variation (CV), can lead to well-informed choices.

**Stability and Growth:** Distinguishing cities with stable and consistent growth trends is paramount. Greenville demonstrates a stable upward trajectory, making it an attractive destination for investors seeking reliable returns. On the other hand, Florence presents a unique case of rapid short-term growth, showcasing potential for substantial returns within a shorter timeframe.

**Seasonal and Cyclical Effects:** Incorporating seasonal patterns into investment decisions can provide a competitive edge. By understanding seasonal fluctuations in property values, APC can strategize purchases and sales to maximize profitability.

# Next Steps
**Dataset Augmentation:** This could improve the predictive accuracy of the choosen model.

**Ensemble Models:** Use an ensemble of the three models to leverage the strengths of each which and yield better results.

























