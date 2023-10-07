# Univariate_Analysis
## ODD2023-DataScience-Ex-03
## Aim
To read the given data and perform the univariate analysis with different types of plots.

## Explanation
Univariate analysis is basically the simplest form to analyze data. Uni means one and this means that the data has only one kind of variable. The major reason for univariate analysis is to use the data to describe. The analysis will take data, summarise it, and then find some pattern in the data.

## Algorithm :
Step1 Read the given data.

Step2 Get the information about the data.

Step3 Remove the null values from the data.

Step4 Mention the datatypes from the data.

Step5 Count the values from the data.

Step6 Do plots like boxplots,countplot,distribution plot,histogram plot.

## Program:
~~~
import pandas as pd
from scipy import stats
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
~~~
~~~
from google.colab import files
uploaded = files.upload()
~~~
~~~
df = pd.read_csv('diabetes.csv')
df
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/a973ea82-a6ff-4536-a989-fde2fa8f2e78)

~~~
df.isnull().sum()
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/4f48c688-bc5d-4a5e-a835-63dd0bd7b25b)

~~~
q1 = df.quantile(0.25)
q3 = df.quantile(0.75)
iqr = q3 - q1
iqr
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/6e7394e5-29f1-4c4a-8a19-30bc83417b1f)

~~~
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
df = df[(df >= low) & (df <= high)]
df
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/4bbfa76a-83e1-4cdd-9010-2efe0d6684c5)

~~~
sns.boxplot(df)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/3565a67f-8913-42af-b94f-d445ed93d7ed)

~~~
sns.displot(x ="Glucose", data = df)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/23549c48-3cc3-4285-8d63-fa7de1cd3b4f)

~~~
sns.displot(x ="BloodPressure", data = df)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/27b0cfcf-2423-4a96-a17f-cfb992c8f3f7)

~~~
sns.displot(x ="BMI", data = df)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/c91b5346-20d6-4595-8f27-272688589d8a)

~~~
sns.displot(x ="DiabetesPedigreeFunction", data = df)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/d5e9fb36-4f18-43a1-a5ab-eb7aa0f0b41f)

~~~
sns.displot(x ="Age", data = df)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/be16d748-0181-4f5b-b1f7-546548236ded)

~~~
from google.colab import files
uploaded = files.upload()
~~~
~~~~
df = pd.read_csv('employeesal.csv')
df
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/4de469de-fe5f-4e08-a80d-42daa0b74005)

~~~
df.isnull().sum()
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/a961b536-3ff6-481f-847f-3d61253c2126)

~~~
numeric_cols = df.select_dtypes(include=[int, float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/68f12eaa-9c6b-4496-b2da-cd3b374de95b)

~~~
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
numeric_cols.dropna()
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/b0d28068-a425-4acb-b0d5-9dc6a0215ab9)

~~~
sns.boxplot(numeric_cols)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/2b9b0e09-a6df-46b9-a48e-03f14c5f37b2)

~~~
sns.histplot(x = 'Experience_Years',data = numeric_cols)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/c233661c-f0d9-432a-a2c1-b475aca1774c)

~~~
sns.histplot(x = 'Age',data = numeric_cols)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/f90366fa-d68d-4282-a0bf-9a8605965906)

~~~
sns.histplot(x = 'Salary',data = numeric_cols)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/a7749edd-a73d-4188-8b84-cb85f34cd35f)

~~~
from google.colab import files
uploaded = files.upload()
~~~
~~~
df = pd.read_csv('SuperStore.csv')
df
~~~
~~~
df.isnull().sum()
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/97041458-4196-4505-98f7-857f013f4f97)

~~~
df.dropna()
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/87458014-ad05-400c-aaf5-aaced7168bfd)

~~~
df.dtypes
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/190f5014-ccea-45df-8b2b-c3787bab0e53)

~~~
numeric_cols = df.select_dtypes(include=[float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/0b9df85a-271b-42e7-96fa-b0b7034bdec4)

~~~
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
~~~
~~~
sns.boxplot(numeric_cols)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/b7e6a4fe-5590-44b7-abc0-e7159f692f11)

~~~
sns.histplot(x = 'Sales',data = numeric_cols)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/7b0f7a20-56eb-465c-a25e-50af43f0570a)

~~~
sns.countplot(x="Postal Code", data=numeric_cols)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/2356e1e8-972a-4846-bf6e-f57a2bbdaa5c)

RESULT:
Thus we have read the given data and performed the univariate analysis with different types of plots.

