# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE
```
import pandas as pd
import numpy as np
df=pd.read_csv("Superstore.csv")

df.head()

# Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt

#1.Line plot

plt.figure(figsize=(8,5))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
sns.lineplot(x="Category",y="Sales",data=df,marker='o')

#2.Scatterplot

sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

#3.Boxplot

sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)

#4.Violin Plot

sns.violinplot(x="Profit",data=df)

#5.Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

#6.Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])

#7.Count plot

sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df)

#8.Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')

#9.KDE Plot

sns.kdeplot(x="Profit", data = df,hue='Category')

#Data Visualization Using MatPlotlib

#1.Plot

plt.plot(df['Category'], df['Sales'])
plt.show()

#2.Heatmap

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)

#3.Piechart

df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()

#4.Histogram


plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()

#5.Bargraph

plt.bar(df.index,df['Category'])
plt.show()

#6.Scatterplot

plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()              

#7.Boxplot

plt.boxplot(x="Sales",data=df)
plt.show()
```
# OUPUT
## Reading the given dataset:
![170985646-ccfbc412-b358-4115-b197-70e373a97404](https://user-images.githubusercontent.com/94219582/171085575-850daf1b-9595-42da-b02d-8c4c5d7c6aca.png)
# Data Visualization Using Seaborn:
## 1.Lineplot
![170985803-c6671117-ccfb-4a94-8132-8e1a258d1593](https://user-images.githubusercontent.com/94219582/171085679-aae1afbe-1db7-4440-8491-d48f8ba90440.png)

![170985838-de8ed4fd-65a9-43ec-a3a0-9bf04017fe45](https://user-images.githubusercontent.com/94219582/171085711-2b03d8d7-8910-4982-b2fe-734faa6b8fc8.png)
## 2.Scatterplot
![170985871-d2732de8-a729-4e59-af26-0868e29d7f3d](https://user-images.githubusercontent.com/94219582/171085780-cedd0de2-e5b5-488a-988a-0659373a2d22.png)
![170985891-e19a83d9-2cd2-40b0-939f-01ef0decec37](https://user-images.githubusercontent.com/94219582/171085794-df911e71-8293-43a4-8ff0-f55b055af1db.png)
## 3.Boxplot
![170985937-0a3b5dae-0306-4d45-b8d4-c278620c2e48](https://user-images.githubusercontent.com/94219582/171085856-61713565-712d-47e7-bf95-a84611b044f1.png)
![170985949-9876aa03-940d-434c-a5cc-b830845e97b3](https://user-images.githubusercontent.com/94219582/171085865-4f7001be-af02-4ae1-a961-cd02ea9b3d38.png)
## 4.Violinplot
![170985994-1b57705e-e411-43ee-8553-b20656e1a7cd](https://user-images.githubusercontent.com/94219582/171085903-b62abd5e-ed57-4cdf-ad1d-9adead1a339d.png)
## 5.Barplot
![170986074-e320e391-d31c-458d-9007-a2a9b4930b71](https://user-images.githubusercontent.com/94219582/171085953-dfd8ae08-2d07-433d-936f-62495220c1ed.png)
![170986095-986ef622-5254-4228-ab6c-0cdba8cf389f](https://user-images.githubusercontent.com/94219582/171085962-1c1a755d-de30-443d-ae3b-f680304c118c.png)
## 6.Pointplot
![170986140-34e896cd-9265-4cc1-98ca-73eb1b600028](https://user-images.githubusercontent.com/94219582/171086011-0336e283-6007-4b98-8cfa-6d5b42c53e27.png)
## 7.Countplot
![170986183-c1fe579c-484c-499a-939f-ea5502ba930b](https://user-images.githubusercontent.com/94219582/171086056-1973e990-37f1-44e4-b5fe-1813db8f8305.png)
## 8.Histogram
![170986236-7d0f5c48-3caa-4b3b-a44a-2613bd777220](https://user-images.githubusercontent.com/94219582/171086086-5424206f-e653-4ee7-874f-8f72e1273fed.png)
## 9.KDE Plot
![170986290-28e2e3f7-1e19-4ca1-bf30-7a9a1e133ac5](https://user-images.githubusercontent.com/94219582/171086130-79c27dc8-1e52-483c-821a-e505bcbdfc39.png)
# Data Visualization Using Matplotlib:
## 1.Plot
![ds1](https://user-images.githubusercontent.com/94219582/171086746-edc3d53b-febc-4f31-bdac-ffe0ca1eb0f5.png)
## 2.Heatmap
![170986395-34027063-a756-4307-a144-7d9e51554528](https://user-images.githubusercontent.com/94219582/171086842-9955d932-2dac-4ba1-8cb9-92783d01af0d.png)
![170986410-eaa8366c-70fc-4bba-b212-8dfd53b39c03](https://user-images.githubusercontent.com/94219582/171086855-960093de-e62d-4c1f-a3e3-58902f55d413.png)

## 3.PieChart
![170986466-330ceaec-c3f0-40ab-a177-92885454b26b](https://user-images.githubusercontent.com/94219582/171086879-8bb2bdde-a899-4515-8397-26fccb28f2d6.png)
![170986481-42e9f0ec-5223-4a87-a553-a649a30a2384](https://user-images.githubusercontent.com/94219582/171086913-7a9f4736-6d76-4c65-8aef-55c8de0a3ce6.png)
## 4.Histogram
![170986533-19a5064d-9acf-456a-adc3-ec4ecdb4765b](https://user-images.githubusercontent.com/94219582/171086927-4fc2a1d5-34a7-41fc-8318-b78810b0b915.png)
## 5.Bargraph
![170986583-f76c12d8-735f-4f9a-977d-3931e5465ca3](https://user-images.githubusercontent.com/94219582/171086940-b16b362f-0157-48d5-b3f7-08735b0e2ad8.png)
## 6.Scatterplot
![170986638-2d06d57b-9b6c-468f-b992-5ad1107b8982](https://user-images.githubusercontent.com/94219582/171087086-ce5fba1d-1856-4e0f-8a20-ffada0ac66d3.png)
## 7.Boxplot
![170986701-51425ca2-db20-4b3e-bb79-73c3cfdcd2c8](https://user-images.githubusercontent.com/94219582/171087099-a24f0cb6-1c49-479a-bd15-adac86d7198b.png)

# RESULT:
Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.




