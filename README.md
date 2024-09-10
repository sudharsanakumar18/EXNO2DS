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
```
```
dt=pd.read_csv("titanic_dataset.csv")
```

```
dt
```
![Screenshot 2024-09-07 210342](https://github.com/user-attachments/assets/2bc226e4-f7dc-451d-9512-4327ff8fe352)

```
dt.info()
```
![image](https://github.com/user-attachments/assets/3551f060-46dd-4317-b38b-156d12ac62c7)

```
dt.describe()
```
![image](https://github.com/user-attachments/assets/e06d043a-00e7-4b08-ad17-5c38a25c1875)

```
dt.shape
```
![image](https://github.com/user-attachments/assets/b89af2a2-6365-4eb6-8e4f-4f4adbc0498f)
```
dt.nunique()
```
![image](https://github.com/user-attachments/assets/43214f4a-3f06-4745-a95e-58ee67459b24)
```
dt["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/e54b778a-3c59-40ec-8a25-fd7c48e3f897)
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/a2195874-a680-4607-bc94-f3743790da49)
```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/user-attachments/assets/a30da629-e518-4c8e-a23c-4ec819cbb40d)
```
dt.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/c0d3156b-8bdf-44a5-bac9-b7b562b18bde)
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```

![image](https://github.com/user-attachments/assets/14cfb01e-2719-41b2-ba8e-e22f31c45c06)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```

![image](https://github.com/user-attachments/assets/9a2553f5-ce2a-441b-97e6-cd095a2c8b3b)
```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```

![image](https://github.com/user-attachments/assets/6a94796e-c22a-4275-90fa-6ae8b1578cb3)
```
dt.boxplot(column="Age",by="Survived")
```

![image](https://github.com/user-attachments/assets/651196ff-89c8-4719-b150-dcfaed081386)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```

![image](https://github.com/user-attachments/assets/9d5fedc1-7d37-47ca-a439-6d66c92284e5)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```

![image](https://github.com/user-attachments/assets/105633c8-7363-420b-a4fb-d46d5b64afe2)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![image](https://github.com/user-attachments/assets/4b4f0e63-00e2-4206-8b19-4aff6e8ac8de)
```
numeric_dt=dt.select_dtypes(exclude=[object])
corr=numeric_dt.corr()
sns.heatmap(corr,annot=True)
```

![image](https://github.com/user-attachments/assets/0f496edc-97e0-4b29-8b0d-1b1059579d8d)
```
sns.pairplot(dt)
```

![image](https://github.com/user-attachments/assets/34900d81-0510-4bcf-9452-4f1906fd4696)

# RESULT
        Thus the data analysis has been implemented succesfully.
