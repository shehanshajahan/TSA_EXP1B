# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
### Name: SHEHAN SHAJAHAN 
### Regno: 212223240154
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Load the data
data = pd.read_csv("AirPassengers.csv")
# Create DataFrame
df = pd.DataFrame(data)

# Regular differencing
df['Regular Difference'] = df['#Passengers'].diff()

# Seasonal adjustment
result = seasonal_decompose(df['#Passengers'], model='additive', period=12)
df['Seasonal Adjustment'] = result.resid

# Log transformation
df['Log Transformation'] = np.log(df['#Passengers'])

# Plotting
plt.figure(figsize=(14, 10))

plt.subplot(4, 1, 1)
plt.plot(df['#Passengers'], label='Original')
plt.legend(loc='best')
plt.title('Original Data')

plt.subplot(4, 1, 2)
plt.plot(df['Regular Difference'], label='Regular Difference')
plt.legend(loc='best')
plt.title('Regular Differencing')

plt.subplot(4, 1, 3)
plt.plot(df['Seasonal Adjustment'], label='Seasonal Adjustment')
plt.legend(loc='best')
plt.title('Seasonal Adjustment')

plt.subplot(4, 1, 4)
plt.plot(df['Log Transformation'], label='Log Transformation')
plt.legend(loc='best')
plt.title('Log Transformation')

plt.tight_layout()
plt.show()
```
### OUTPUT:

#### ORIGINAL DATA:
<img width="1141" height="233" alt="o1" src="https://github.com/user-attachments/assets/0f7ff556-dcb2-4c52-ba3e-8082f18c097e" />

#### REGULAR DIFFERENCING:
<img width="563" height="146" alt="o2" src="https://github.com/user-attachments/assets/e1babfb1-d20b-4b1d-baba-2b7cdddc599f" />


#### SEASONAL ADJUSTMENT:
<img width="544" height="146" alt="o3" src="https://github.com/user-attachments/assets/9a8a02a0-75d4-4733-8a03-4b2c0d1142b2" />



#### LOG TRANSFORMATION:
<img width="630" height="144" alt="o4" src="https://github.com/user-attachments/assets/44a4d81e-9b9a-417b-9bae-261796ca29fa" />




### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
