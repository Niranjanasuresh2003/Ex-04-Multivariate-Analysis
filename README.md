# Ex-04-Multivariate-Analysis


AIM

To perform Multivariate EDA on the given data set.

Explanation:

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

ALGORITHM:

##STEP 1

Import the built libraries required to perform EDA and outlier removal.

##STEP 2

Read the given csv file

##STEP 3

Convert the file into a dataframe and get information of the data.

##STEP 4

Return the objects containing counts of unique values using (value_counts()).

##STEP 5

Plot the counts in the form of Histogram or Bar Graph.

##STEP 6

Use seaborn the bar graph comparison of data can be viewed.

##STEP 7

Find the pairwise correlation of all columns in the dataframe.corr()

##STEP 8

Save the final data set into the file

PROGRAM
~~~

Name : NIRANJANA DEVI S
Register Number : 212220220036

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("SuperStore.csv")
df
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sns.scatterplot(df['Row ID'],df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Row ID"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Row ID")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("ROW ID")
plt.show()
states=df.loc[:,["Segment","Row ID"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("ROW ID")
plt.show()
sns.barplot(df['Sales'],df['Ship Mode'],hue=df['Region'])
df.corr()
sns.heatmap(df.corr(),annot=True)
~~~

#OUTPUT

##DATA

![image](https://user-images.githubusercontent.com/129851738/230834576-9bf84bad-fcca-4ae1-9bea-336618ffc71e.png)

##Data.info

![image](https://user-images.githubusercontent.com/129851738/230834878-b4153af0-d2a4-4025-87c9-de93e00bd4ee.png)

##Data.describe

![image](https://user-images.githubusercontent.com/129851738/230835262-5b204e15-edf8-48b8-9dc4-ef9a2d1846b6.png)

##Checking the null values and Cleaning it

![image](https://user-images.githubusercontent.com/129851738/230835500-49345bb9-430a-41c3-85bd-d498c2b48459.png)

![image](https://user-images.githubusercontent.com/129851738/230835554-c109fff9-08c4-41b4-9487-de8402754fc5.png)

##DATA TYPES

![image](https://user-images.githubusercontent.com/129851738/230835641-d81bdb7a-a077-4b10-a383-092802be084b.png)

##SCATTER PLOT

![image](https://user-images.githubusercontent.com/129851738/230835742-498271f9-0852-42b2-8fd1-63665c14e00e.png)

##BAR PLOT

![image](https://user-images.githubusercontent.com/129851738/230835809-97474c9e-0760-4f6f-833d-c7daa98ae538.png)


![image](https://user-images.githubusercontent.com/129851738/230835862-ff193131-df61-4fc1-ba82-936a7129a0d1.png)


![image](https://user-images.githubusercontent.com/129851738/230835898-39756bfd-a168-469a-ba9b-1e530a48c954.png)


![image](https://user-images.githubusercontent.com/129851738/230835926-68f14d0f-feb9-481e-8e96-36051d4c84ca.png)

##CORRELATION COEFFICIENT INTERPRETATION

![image](https://user-images.githubusercontent.com/129851738/230836014-f0b690cf-ac1b-48dc-923a-0586994a6e85.png)

##HEATMAP

![image](https://user-images.githubusercontent.com/129851738/230836101-9629b535-eda6-42d7-8316-84f6b4637a71.png)

#RESULT

Thus we have read the given data and performed the multivariate analysis with different types of plots.




