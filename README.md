# EXNO2DS
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
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/Lokhnath10/EXNO2DS/assets/138969918/04879ce0-bd42-4f96-8239-5da905099df5)
```
df.head()
```
![image](https://github.com/Lokhnath10/EXNO2DS/assets/138969918/62b8f167-67f8-4731-b30d-dd576849be1b)
```
df.tail()
```
![image](https://github.com/Lokhnath10/EXNO2DS/assets/138969918/56b53cf0-93d0-461e-bbc0-586c6b352005)
```
df.nunique()
```
![image](https://github.com/Lokhnath10/EXNO2DS/assets/138969918/afe03dd9-9514-4643-9404-981a9527dbb9)
```
df["Survived"].value_counts()
```

![image](https://github.com/Lokhnath10/EXNO2DS/assets/138969918/6fc646ff-722f-4df6-a7a6-3bfa2008e8f5)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```

![image](https://github.com/Lokhnath10/EXNO2DS/assets/138969918/dd14fb07-841d-441e-bb7e-3610c0870ddc)
```
sns.countplot(data=df,x="Survived")
```

![image](https://github.com/Lokhnath10/EXNO2DS/assets/138969918/44e75547-aa89-4779-a3aa-d8222541e404)
```
df.Pclass.unique()
```

![image](https://github.com/Lokhnath10/EXNO2DS/assets/138969918/9057a7f1-9322-475d-af37-f51f38f69e28)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

![image](https://github.com/Lokhnath10/EXNO2DS/assets/138969918/7eb551a5-aab4-4796-b3b3-9c62cbc96b24)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

![image](https://github.com/Lokhnath10/EXNO2DS/assets/138969918/071a1059-1093-4929-ae81-791bba335649)
```
sns.catplot(x='Survived',hue="Gender",data=df,kind="count")
```

![image](https://github.com/Lokhnath10/EXNO2DS/assets/138969918/077b83b0-c3b9-4b8f-8502-cf8fd4874f19)
```
df.boxplot(column="Age",by="Survived")
```

![image](https://github.com/Lokhnath10/EXNO2DS/assets/138969918/a9340db5-8d7e-41a8-a8e1-e9ea3cba7916)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

![image](https://github.com/Lokhnath10/EXNO2DS/assets/138969918/b13f5ac4-7c97-4b29-a1e0-2a2c6031171c)
```
fig, ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

![image](https://github.com/Lokhnath10/EXNO2DS/assets/138969918/8c54ffbc-a7bf-4a41-bc43-be85380571a7)
```
corr=df.corr()
sns.heatmap(corr,annot=True)
```

![image](https://github.com/Lokhnath10/EXNO2DS/assets/138969918/50572a7d-a49b-4e01-ae93-4925dcc0c627)


# RESULT 
The EDA Analysis using python is executed successfully.
