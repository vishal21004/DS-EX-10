# Flight information -analysis

## AIM :

To Perform Bivariate/Multivariate Analysis

## ALGORITHM :

1.Read the given data

2.Get information from the data

3.Perform the Multivariate Analysis

4.Save the clean data to file

## PROGRAM :

Developed by: Sathiya Narayanan G

Reg no: 212221220049

import pandas as pd

import numpy as np

import seaborn as sns

import matplotlib.pyplot as plt

import io

from google.colab import files

uploaded = files.upload()

dd = pd.read_csv(io.BytesIO(uploaded['FlightInformation.csv']))

print(dd)

## TYPES OF BIVARIATE ANALYSIS:

### (i) Numerical & Numerical

sns.scatterplot (dd['Date_of_Journey'],dd['Dep_Time'])

![image](https://user-images.githubusercontent.com/119560261/229037607-1573e69c-5e28-4c9a-8b52-cef0b38a9be7.png)

### (ii) Numerical & Categorical

sns.barplot (x=dd['Duration'],y=dd['Price'])

![image](https://user-images.githubusercontent.com/119560261/229037776-97b0e5a9-6bb2-4718-a9b7-4de3202fa226.png)

sns.barplot(x=dd["Arrival_Time"],y=dd["Price"],data=dd)

![image](https://user-images.githubusercontent.com/119560261/229037892-1d807fbb-e11a-4a11-9582-ba386b267331.png)

states=dd.loc[:,["Duration","Price"]]

states=states.groupby(by=["Duration"]).sum().sort_values(by="Price")

sns.barplot(x=states.index,y="Price",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Duration")

plt.ylabel=("Price")

plt.show()

![image](https://user-images.githubusercontent.com/119560261/229037987-b681d332-1d02-44d5-854e-6b1cb824f073.png)

## Multivariate Analysis :

dd.corr()

data = np.random.randint(low = 1, high = 100, size = (10, 10))

print("The data to be plotted:\n")

print(data)

hm = sns.heatmap(data = data)

plt.show()

![image](https://user-images.githubusercontent.com/119560261/229038165-2ce3fc02-0ba4-4e37-a3b6-14f0c16b9bf8.png)

## RESULT:

Thus, Bivariate/Multivariate Analysis is performed successfully.
