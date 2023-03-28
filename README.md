Ex03-Univariate-Analysis
Aim
To read the given data and perform the univariate analysis with different types of plots.

Explanation
Univariate analysis is basically the simplest form to analyze data. Uni means one and this means that the data has only one kind of variable. The major reason for univariate analysis is to use the data to describe. The analysis will take data, summarise it, and then find some pattern in the data.

Algorithm
Step1
Read the given data.

Step2
Get the information about the data.

Step3
Remove the null values from the data.

Step4
Mention the datatypes from the data.

Step5
Count the values from the data.

Step6
Do plots like boxplots,countplot,distribution plot,histogram plot.

Program:
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/SuperStore.csv")
df
df.info()
df.isnull().sum()
df['Postal Code']=d['Postal Code'].fillna(d['Postal Code'].mode()[0])
df.head()
df.boxplot()
df['Ship Mode'].value_counts()
df['Segment'].value_counts()
df['City'].value_counts()
df['State'].value_counts()
df['Region'].value_counts()
df['Category'].value_counts()
df['Sub-Category'].value_counts()
df_count = df.groupby(by=["Category"]).count()
df_sum = df.groupby(by=["Category"]).sum()
labels=[]
for i in df_count.index:
    labels.append(i)
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
myexplode = [0, 0.2,0]
plt.pie(df_count["Sales"], colors = colors,explode = myexplode, labels=labels, autopct = "%0.0f%%",shadow = True) 
plt.show()
```
