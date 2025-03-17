# Ex.No: 1B CONVERSION OF NON STATIONARY TO STATIONARY DATA
## DATE: 

## AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data.

## ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
   
## PROGRAM :

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
data = pd.read_csv('Gold Price Prediction.csv')
date_column = 'Date'
price_column = 'Price Today'
data[date_column] = pd.to_datetime(data[date_column])
x = data[date_column]
y = data[price_column]
plt.figure(figsize=(10, 5))
plt.xlabel('Date')
plt.ylabel(price_column)
plt.plot(x, y, label="Original Data")
plt.legend()
plt.show()
data['diff'] = data[price_column].diff()
data.dropna(inplace=True)
x = data[date_column]
y = data['diff']
plt.figure(figsize=(10, 5))
plt.xlabel('Date')
plt.ylabel('Differenced Data')
plt.plot(x, y, label="Differenced Data", color='r')
plt.legend()
plt.show()
data['SeasonalAdjustment'] = data[price_column] - data[price_column].rolling(window=12).mean()
data.dropna(inplace=True)
x = data[date_column]
y = data['SeasonalAdjustment']
plt.figure(figsize=(10, 5))
plt.xlabel('Date')
plt.ylabel('Seasonally Adjusted Data')
plt.plot(x, y, label="Seasonal Adjustment", color='g')
plt.legend()
plt.show()
data['log'] = np.log(data['diff'])
data.dropna(inplace=True)
x = data[date_column]
y = data['log']
plt.figure(figsize=(10, 5))
plt.xlabel('Date')
plt.ylabel('Log Transformed Data')
plt.plot(x, y, label="Log Transformation", color='m')
plt.legend()
plt.show()
```
## OUTPUT :

### ORIGINAL DATA :
![image](https://github.com/user-attachments/assets/56b5f421-3d4b-4026-8df8-f845a0d71e9b)

### REGULAR DIFFERENCING :
![image](https://github.com/user-attachments/assets/99fbf035-f484-4915-937f-fece89e89e36)

### SEASONAL ADJUSTMENT :
![image](https://github.com/user-attachments/assets/8ac4d8fe-282d-4191-953f-8c8d19a13678)

### LOG TRANSFORMATION :
![image](https://github.com/user-attachments/assets/c61c4364-c65a-4109-94a9-7f89dbb38993)

 
## RESULT :
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
