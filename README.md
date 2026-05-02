# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
Date: 02.04.2026

### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.
### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
### PROGRAM:

```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.graphics.tsaplots import plot_acf

# Load the dataset
file_path = r'C:\Users\admin\Desktop\Sem lab\TSA\FINAL_USO.csv'  # Replace with your actual file path
data = pd.read_csv(file_path)

# Convert 'Date' to datetime format
data['Date'] = pd.to_datetime(data['Date'], format='%Y-%m-%d')
data.set_index('Date', inplace=True)

# Use the 'Close' column for ACF calculation
price_today = data['Close']

# Compute and plot ACF for the first 35 lags
plt.figure(figsize=(10, 6))
plot_acf(price_today, lags=35, alpha=0.05)  # ACF with 35 lags and confidence intervals
plt.title('AutoCorrelation Function (ACF) for Gold Price')
plt.xlabel('Lags')
plt.ylabel('ACF Value')
plt.grid(True)
plt.show()

```

### OUTPUT:
<img width="587" height="455" alt="image" src="https://github.com/user-attachments/assets/a4809214-4533-48b8-a529-4806e928994b" />

### RESULT:
        Thus we have successfully implemented the auto correlation function in python.
