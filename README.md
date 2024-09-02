
# EXNO2DS
# Name: Piritharaman R
# Reg no: 212223230148

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
![image](https://github.com/user-attachments/assets/11d713c7-a90b-42b2-9138-b697988dfd1b)
```
df.info()
```
![image](https://github.com/user-attachments/assets/e68c78bd-4488-474d-9280-53aca57279ab)
```
df.shape
```
![image](https://github.com/user-attachments/assets/939e36be-caa6-4600-8286-9c1996816802)
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/cedd1720-ebbf-4605-aa4c-60e702f636f6)
```
df.shape
```
![image](https://github.com/user-attachments/assets/ef94a23a-1c88-43c8-b133-8e35ec5d63d2)

# Categorical data analysis
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/1fa7b45f-8523-4231-a26d-ec2bf25e2edf)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/87a19de3-91e1-4d51-a532-36dc9a71d917)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/a672d12e-a75b-42b5-ae6c-279d46399da8)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/87f904ba-6015-4ef0-a843-55cc7d3bebad)
```
df
```
![image](https://github.com/user-attachments/assets/04193d8e-c43f-42ee-b4b3-20f62cd47e64)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/0890ec3f-4ac8-44ef-812b-58f3f0414e4d)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/891b4b86-44df-4b92-853c-7f0cb35fe8f9)

# Bivariate Analysis
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/ed5decce-d886-422e-a907-4f91e600b6e9)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/f61e4f6a-b7c4-44d7-8540-4527fbc320cc)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/a425a90b-766d-4623-b2c1-e96fa1a2abf1)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/9fbf1e10-04ce-421d-8184-b7f2807a2bf2)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/cc0b7552-9b04-4fb6-b82a-1ba0f8a81872)

# Multivariate Analysis
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/7f4b63df-bc22-4be2-b758-9eb71588f945)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/edb2e6f8-9f1c-4e42-9a77-3df363265456)

# Co-relation
```
df_numeric = df.select_dtypes(include=['number'])
corr=df_numeric.corr()
sns.heatmap(corr,annot=True)
plt.show()
```
![image](https://github.com/user-attachments/assets/613cde15-426a-4388-ad3c-47045c1b6025)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/45977dc8-7b5f-4ada-b6fb-0508e6d564e6)
![image](https://github.com/user-attachments/assets/e635a280-e475-4d7e-89d6-48b5c0cfd937)
![image](https://github.com/user-attachments/assets/91f90e2e-18c0-4cdf-8fbc-99679fc49847)


# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
