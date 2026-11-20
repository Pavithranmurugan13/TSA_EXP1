# Ex.No: 01A PLOT A TIME SERIES DATA

###  Date: 18/11/2026

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:

```
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("Apple_Stock.csv")
df.head()

df.drop([' Volume', ' Open', ' High', ' Low'], axis=1, inplace=True)
df.head()
df.columns = df.columns.str.strip()
df.columns
df.head()

df['Close/Last'] = df['Close/Last'].replace('[\$,]', '', regex=True).astype(float)
df.head()

df['Date'] = pd.to_datetime(df['Date'])
df = df.sort_values(by='Date')
df.set_index('Date', inplace=True)
df.head()

plt.figure(figsize=(12,6))
plt.plot(df.index, df['Close/Last'])
plt.title('Stock Price Trend')
plt.xlabel('Date')
plt.ylabel('Price $')
plt.grid()
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

# OUTPUT:

## Dataset

![alt text](output/Dataset.png)

## Cleaned Data

![alt text](output/cleaned.png)

## Plot

![alt text](output/plot.png)

# RESULT:
Thus we have created the python code for plotting the time series of given data.
