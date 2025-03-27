# EX NO: 2 DS
# Name : TIMMAPURAM YOGEESWAR
# Reg no: 212223230233
# AIM:
To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT:

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns  
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/94fb7707-08c0-4be3-aef3-cfad84f2538f)

```
df.info()
```
![image](https://github.com/user-attachments/assets/534103bc-8bda-4460-98f4-8f9d72533bde)

```
df.shape
```
![image](https://github.com/user-attachments/assets/ac05190a-749d-4bca-b0fe-d16d89a5fe14)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/7c1e03e2-c0ec-4208-8a96-770a45f2160a)

```
df.shape
```
![image](https://github.com/user-attachments/assets/2b5f970d-685e-40a7-b7c6-8df9d4fbf6fd)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/30b58ace-85cb-4c8d-9515-eb037beb50c5)

```
 df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/c0b225a9-5826-4e74-92bb-b08195986ebd)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/b024ac3a-1588-4b1d-ac30-447a3fd16afb)

```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/93db72fe-c79b-4e48-879f-7fdb6d9378e3)

```
df
```
![image](https://github.com/user-attachments/assets/14ae9443-94ea-4981-9fb5-5b773524e1ab)

```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/d2e40eaf-87a3-44f5-8cb6-a150a11bdf09)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/866bfdb8-ed03-4716-8826-7c9aff5da736)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/e660ac50-8fd6-47ba-a5c1-90a4a460f07b)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/cc095d11-9755-41cc-bbd1-76afb070ef29)

```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/44694357-e1f9-477c-acf5-f7a0cd68571b)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/d37bd863-bcac-48d1-a3ca-74dfd51f7a78)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/d8349c69-7710-48f4-b350-115e6c957fd1)

```
 fig, ax1 = plt.subplots(figsize=(8,5))
 plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/007abd21-a7dd-4e96-a50c-72e66ea0d4d2)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/27b22e43-a2f5-4652-a97f-7d6dc56a1ecc)

```
numerical_df = df.select_dtypes(include=['number'])
corr = numerical_df.corr()
sns.heatmap(corr, annot=True)

```
![image](https://github.com/user-attachments/assets/54f12d57-5027-4d49-8f4e-09c210642ab7)

```
 sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/74bac158-7059-4f40-b54d-dde9060da44b)


# RESULT:
Thus, the Exploratory Data Analysis on the given data set was performed successfully.
