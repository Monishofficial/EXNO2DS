# EXNO:2 - DS
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
### Developed By: MONISH N
### Reg No: 212223240097

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![Screenshot 2025-03-27 113402](https://github.com/user-attachments/assets/e4d44ff6-43d4-48c6-b793-7037d23d10db)
```
df.info()
```
![Screenshot 2025-03-27 113546](https://github.com/user-attachments/assets/7eea01dc-68b5-4776-b714-168a9a335b50)
```
df.shape
```
![Screenshot 2025-03-27 113638](https://github.com/user-attachments/assets/47583dbe-a492-4f9c-89cd-5c85a3ae9981)
```
df.nunique()
```
![Screenshot 2025-03-27 113717](https://github.com/user-attachments/assets/8d3a364f-b8f2-4212-9f07-ca463b612118)
```
df["Survived"].value_counts()
```
![Screenshot 2025-03-27 113816](https://github.com/user-attachments/assets/110aecbe-e087-41c9-b812-b14a77dfa3cc)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![Screenshot 2025-03-27 113917](https://github.com/user-attachments/assets/4c9c43c0-ffc4-4db5-896c-0eb89378e700)
```
sns.countplot(data=df,x="Survived")
```
![Screenshot 2025-03-27 113959](https://github.com/user-attachments/assets/09b29f76-017c-45d5-913e-728c63ca08ee)
```
df.Pclass.unique()
```
![Screenshot 2025-03-27 114049](https://github.com/user-attachments/assets/9ca49804-873e-4a7f-9e6e-c53a152f95fd)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![Screenshot 2025-03-27 114131](https://github.com/user-attachments/assets/f6c29e20-0151-4472-9a0b-792fff602b56)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![Screenshot 2025-03-27 114407](https://github.com/user-attachments/assets/4f4dfa65-70c6-4cb2-8059-a2a62ed950b6)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![Screenshot 2025-03-27 114454](https://github.com/user-attachments/assets/d858f6f4-5dc7-44e3-98c1-8ca22737f989)
```
df.boxplot(column="Age",by="Survived")
```
![Screenshot 2025-03-27 114540](https://github.com/user-attachments/assets/d5b1c49c-7ead-4cd3-ac0c-c83fc4f38bff)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![Uploading Screenshot 2025-03-27 114621.png…]()
```
sns.jointplot(x="Age",y="Fare",data=df)
```
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![Screenshot 2025-03-27 114812](https://github.com/user-attachments/assets/a1737c29-0529-439f-b834-12ee44482020)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

```
numerical_df = df.select_dtypes(include=['number'])
corr = numerical_df.corr()
sns.heatmap(corr, annot=True)
```

```
sns.pairplot(df)
```





















       

# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
