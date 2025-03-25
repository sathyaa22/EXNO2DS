# EXNO2DS
      
## NAME: SATHYAA R
## REG NO: 212223100052

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

## CODING AND OUTPUT

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

```
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/0fca64fd-3a1a-4ac4-a552-02ca7f452796)


```
df.info()
```
![image](https://github.com/user-attachments/assets/ff7ef69c-a6da-4e61-b553-667a813e452a)


```
df.shape
```
![image](https://github.com/user-attachments/assets/f252eaa1-1ba0-4bb7-8825-e88f1b10959a)


```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/2d8d955f-9038-4b00-b281-fde3978d349f)


```
df.shape
```
![image](https://github.com/user-attachments/assets/4b5d6a6d-ac12-4398-a604-947fd9f38ffe)


```
# Categorical data analysis
df.nunique()
```
![image](https://github.com/user-attachments/assets/e46f4665-d521-466c-b007-8020337f86e9)


```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/afc78b02-60d7-42de-bc07-e919ed49e948)


```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/394521f3-731e-4d65-9f09-1b7a72227ea3)


```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/faf551b3-ba9c-40d2-84e7-06b55ab23315)


```
df
```
![image](https://github.com/user-attachments/assets/bc91d11f-b0e9-4aea-90ac-5d421e065426)


```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/7daffa5e-0ba9-4f17-84d2-fa4924378d73)


```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/1e90a26a-e277-4f6a-9f41-b15e2b5fa96b)


```
# Bivariate analysis
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/1c28d5e8-ebce-4721-9a09-f441d37fb61f)


```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/db38de8e-1228-43a3-88f4-45852752c1aa)


```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/b0a3ef19-c223-40b7-92aa-4ac9ebf3e7f1)


```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/7537392b-bc90-4923-af79-f3106b298ecf)


```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/30868012-1682-4799-8fa4-a8fe1a089f1e)


```
# Multivariate analysis
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/4a572886-14a5-47c3-b90b-d724ad9e9355)


```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/a748a19b-f78e-4a90-a81f-6bab8e553a26)


```
# Co-relation
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/c0a356cb-9e68-4f86-9e49-b5b9e1068b7b)


```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/e292c39a-1395-4074-a259-c114b09b4dd5)



# RESULT:
We have performed Exploratory Data Analysis on the given data set successfully.
