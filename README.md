# Ex-04-Multivariate-Analysis

# AIM

To perform Multivariate EDA on the given data set.

# Explanation

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM

# STEP 1

Import the built libraries required to perform EDA and outlier removal.

# STEP 2

Read the given csv file

# STEP 3

Convert the file into a dataframe and get information of the data.

# STEP 4

Return the objects containing counts of unique values using (value_counts()).

# STEP 5

Plot the counts in the form of Histogram or Bar Graph.

# STEP 6

Use seaborn the bar graph comparison of data can be viewed.

# STEP 7

Find the pairwise correlation of all columns in the dataframe.corr()

# STEP 8

Save the final data set into the file

# CODE

```

import pandas as pd
import numpy as np
import seaborn as sbn
import matplotlib.pyplot as plt
df = pd.read_csv("/content/SuperStore.csv")
df.head(10)
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sbn.scatterplot(df['Postal Code']),(df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Postal Code"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code")
plt.figure(figsize=(17,7))
sbn.barplot(x=states.index,y="Postal Code",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("Postal Code")
plt.show()
states=df.loc[:,["Segment","Sales"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")
#plt.figure(figsize=(10,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("SALES")
plt.show()
sbn.barplot(data=df, x="Postal Code", y="Ship Mode", hue="Region")
df.corr()
sbn.heatmap(df.corr(),annot=True)

```
# Output

# EDA-Superstore.csv

![image](https://user-images.githubusercontent.com/118361409/235066186-60e2f02a-3c06-4604-95dc-1e3896b01140.png)


Displaying information about Dataset

![image](https://user-images.githubusercontent.com/118361409/235066447-cbae797a-1147-4fb8-aa07-9addbad995b0.png)

Checking the null values and Cleaning it

![image](https://user-images.githubusercontent.com/118361409/235066518-cc2a3f4d-b1f4-4b56-993b-7c1789dbce8f.png)

Displaying datatypes of each features

![image](https://user-images.githubusercontent.com/118361409/235066576-91f0023a-ad6f-4193-a625-42d9ea18e88a.png)


Multivariate Analysis - Scatterplot

![image](https://user-images.githubusercontent.com/118361409/235066688-fbcc0898-04f4-4a47-b820-56822b798156.png)


Multivariate Analysis - Barplot

![image](https://user-images.githubusercontent.com/118361409/235066731-7079fc16-2f26-4fa5-a54f-6a0fa6fd7e02.png)

![image](https://user-images.githubusercontent.com/118361409/235068243-e8f0454d-e927-444d-b707-4f4bd73c8459.png)


![image](https://user-images.githubusercontent.com/118361409/235067138-3de66e0b-e4ce-47ae-a1e4-f98cddd3077b.png)

![image](https://user-images.githubusercontent.com/118361409/235067187-681166d8-4c59-4fcc-adf0-65ef4f0d5d53.png)


Correlation Coefficient Interpretation using HeatMap

![image](https://user-images.githubusercontent.com/118361409/235067223-77b63782-f773-4855-8665-5342eb27a754.png)


# RESULT

Thus the program to perform EDA on the given data set is successfully executed
