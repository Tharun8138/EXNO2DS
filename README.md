## EXNO2DS
## DEVELOPED BY : THARUN V
## REGISTER NO : 212224230290

## AIM:
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
df=pd.read_csv("titanic_dataset.csv")
df
```
![Screenshot 2025-03-27 113932](https://github.com/user-attachments/assets/477a8139-ebfa-4c78-8db1-be739a1db35e)
```
df.info()
```
![Screenshot 2025-03-27 113946](https://github.com/user-attachments/assets/dd233468-6920-462f-91c6-932e43473959)
```
df.shape
```
![Screenshot 2025-03-27 113959](https://github.com/user-attachments/assets/00cd2f53-1ca5-4bc2-ba9b-cd21e8a7dcdd)
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![Screenshot 2025-03-27 114008](https://github.com/user-attachments/assets/3ffab54d-64da-4dd2-ad58-0b1039921df0)
```
df.shape
```
![Screenshot 2025-03-27 114021](https://github.com/user-attachments/assets/c0eee503-4d07-42ff-b3e1-e132a9090d81)
```
df.nunique()
```
![Screenshot 2025-03-27 114032](https://github.com/user-attachments/assets/a1572fd5-6e59-4575-9975-d5497f1db33d)
```
df["Survived"].value_counts()
```
![Screenshot 2025-03-27 114042](https://github.com/user-attachments/assets/2ecc29d6-8682-4c78-9d10-9934d26ac8e4)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![Screenshot 2025-03-27 114050](https://github.com/user-attachments/assets/5799b83d-1c70-47c0-917e-e8c37757877b)
```
sns.countplot(data=df,x="Survived")
```
![Screenshot 2025-03-27 114101](https://github.com/user-attachments/assets/884e4886-96df-4df6-b86d-2770f75e09ec)
```
df
```
![Screenshot 2025-03-27 114113](https://github.com/user-attachments/assets/32360ce0-edd1-484b-947b-a9e2a1c71b48)
```
df.Pclass.unique()
```
![Screenshot 2025-03-27 114209](https://github.com/user-attachments/assets/a732524c-1e67-456f-bdf4-39a318ef5f52)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![Screenshot 2025-03-27 114219](https://github.com/user-attachments/assets/db14dd55-62e9-4e1f-b5b8-65d23a1d2fe9)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![Screenshot 2025-03-27 114230](https://github.com/user-attachments/assets/287b9fca-533c-4379-90ed-39068a9ba7e5)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![Screenshot 2025-03-27 114244](https://github.com/user-attachments/assets/607475e0-5120-45c7-b9ee-773655c18ddf)
```
df.boxplot(column="Age",by="Survived")
```
![Screenshot 2025-03-27 114256](https://github.com/user-attachments/assets/4de2d0c3-8a4e-4ad9-8ad9-09a4ee900e50)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![Screenshot 2025-03-27 114317](https://github.com/user-attachments/assets/7c4346b7-0604-48a2-a9c2-9dd54ac2f66f)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![Screenshot 2025-03-27 114331](https://github.com/user-attachments/assets/ed17707e-8631-43be-99c3-b33532a33cd5)
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![Screenshot 2025-03-27 114343](https://github.com/user-attachments/assets/90e899fd-7684-4485-a66e-a62bb912bdab)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![Screenshot 2025-03-27 114356](https://github.com/user-attachments/assets/97dac10d-6c68-4299-ad2c-8e9f711f1fb9)
```
numerical_features = df.select_dtypes(include=['number'])
corr = numerical_features.corr()
sns.heatmap(corr, annot=True)
```
![Screenshot 2025-03-27 114411](https://github.com/user-attachments/assets/55f49d97-106f-4b6d-abc8-473c0dd09b83)
```
sns.pairplot(df)
```
![Screenshot 2025-03-27 114437](https://github.com/user-attachments/assets/46f6ac17-cf73-4183-a50b-62d74cd6e6b3)
![Screenshot 2025-03-27 114454](https://github.com/user-attachments/assets/02d86f90-7291-40d3-b278-199001ef0902)

# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
