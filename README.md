# Grocery-Store-Sales-Time-Series-Forecasting
Time-series forecasting to forecast store sales on data from Corporación Favorita, a large Ecuadorian-based grocery retailer.

## Source:
This is part of a Kaggle competition dataset: https://www.kaggle.com/competitions/store-sales-time-series-forecasting

## Goal:
For grocery stores, more accurate forecasting can decrease food waste related to overstocking and improve customer satisfaction. 

## Dataset Description
We  will predict sales for the thousands of product families sold at Favorita stores located in Ecuador. 
The training data includes dates, store and product information, whether that item was being promoted, and sales numbers. 
Additional files  like Daily oil price and holiday events include supplementary information that will be useful in building models.

## Data Cleaning and Preparation
The null values of the date dataset is handled.
We also fill in missing dates in the oil price data and then handle any gaps in the oil price values using linear interpolation. 
This is important for time series analysis, where continuous data is crucial for accurate modeling.
Full date details is joined with oil dates


## Observations:
1. Average Sales and Seasonality

- The spread of the red dots around the blue line seems to widen over time. This could indicate that as sales have grown, the variability in daily sales has also increased.
![image](https://github.com/user-attachments/assets/e94bab1e-5e22-4ee5-adb0-e06911aea9c8)


- It is interesting to observe that the weekly and monthly average curves are very similar, while the annual average is quite different from them. The latter curve is strongly influenced by the first minimum.
![image](https://github.com/user-attachments/assets/d719c43f-e29d-4064-99e1-c379ca52ea22)

- A moving average plot shows what kind of trend the series has. Since this series has daily observations, it is good to choose a window of 365 days to smooth over any short-term changes within the year.
![image](https://github.com/user-attachments/assets/3de15e1e-cc92-4cb5-a922-7b0878f36be3)

- By fitting the sales data by linear regression, it is possible to get a very rough description of their trend and also to get a preliminary forecast of the future sales.
- The model predicts sales based purely on the passage of time, ignoring any seasonal or cyclical effects. The predicted values (y_pred) represent the fitted linear trend in the sales data, which can be used for forecasting future sales over a specified period (like 6 months).
![image](https://github.com/user-attachments/assets/745da394-27ab-480f-9f89-46a5cac675ad)

- The figure (top half) shows a clear weekly pattern, with the sales going up in the second part of the week.
There are some clear seasonal features. The most evident is the weekly seasonality, which is also suggested by the above seasonal plot. 
But there are also other features, like the semiweekly and the biweekly peaks.
![image](https://github.com/user-attachments/assets/b3e346e2-2220-4d74-8aaf-a32c194461df)

- Similarly to the above seasonal plot, the periodogram is used to underline the possible presence of periodic features in the time series.
![image](https://github.com/user-attachments/assets/a8ca17cd-c9b1-4041-8509-57311ddeb2a8)

- We then calculate 180 day forecast
![image](https://github.com/user-attachments/assets/84b5f830-6eff-4ab9-8691-5d2fe1579664)

2. Oil Price vs Sales vs Promotions:

- It seems like that the average sales have gone up when the oil prices were low and high and less sales were there when the oil prices were medium.
![image](https://github.com/user-attachments/assets/47555c17-7b71-4221-a35e-e84bce7649ce)

- The plot and its linear interpolation show that stores promote items only when the oil price is medium/low.
![image](https://github.com/user-attachments/assets/9e192f51-92b7-4df7-9392-f580bea88054)

- As expected, the average sales increase when there are items on promotion.
![image](https://github.com/user-attachments/assets/484883cf-6ec2-4004-bfc5-fc69652ee164)


3. Sales per Season, by Store and Article Type

![image](https://github.com/user-attachments/assets/a23783b4-1510-4b40-805d-1468627714f1)

![image](https://github.com/user-attachments/assets/e0bfc94c-18e6-4e26-b5af-46170d67d87f)

![image](https://github.com/user-attachments/assets/76b74529-568b-4f99-8994-911d02395e6a)



## Citation
Alexis Cook, DanB, inversion, Ryan Holbrook. (2021). Store Sales - Time Series Forecasting. Kaggle. https://kaggle.com/competitions/store-sales-time-series-forecasting
