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

Output:

Dataset

![ds3 1](https://user-images.githubusercontent.com/119559844/230063235-b100b7eb-89c0-4975-b70f-8ae4fb6a5803.png)

DATA INFO

![ds3 2](https://user-images.githubusercontent.com/119559844/230063309-c6a10899-4df7-4664-a54b-7cf149eda6cf.png)

DATA NULL

![ds 3 3](https://user-images.githubusercontent.com/119559844/230063345-c2090a95-e01b-4e35-89ed-8ab284a17783.png)

APPLYING MODE TO CLEAN THE DATA

![ds3 4](https://user-images.githubusercontent.com/119559844/230064215-dc359ec3-eb4a-4b35-b6c1-3b79920807ed.png)


BOX-PLOT

![ds3 5](https://user-images.githubusercontent.com/119559844/230064001-fd8e81a6-8499-46ba-9202-086805dbf361.png)


UNIVARIATE - CATEGORY

![ds3 6](https://user-images.githubusercontent.com/119559844/230064055-13b601c5-c36d-4e2a-83ed-e2df2d267771.png)


Result:

Thus we have read the given data and performed the univariate analysis with different types of plots.


