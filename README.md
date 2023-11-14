
# Ex-03 Univariate Analysis
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
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/15b216be-6566-49ca-85fc-870e49e268e8)

~~~
df.isnull().sum()
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/18de4ff5-0502-4bb2-aa73-44eaceac0b86)

~~~
q1 = df.quantile(0.25)
q3 = df.quantile(0.75)
iqr = q3 - q1
iqr
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/e8e9fbee-33a1-4072-b03a-9839683f5ae6)

~~~
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
df = df[(df >= low) & (df <= high)]
df
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/086bfe2b-cf86-4066-bf8b-9e7ccc1707ae)

~~~
sns.boxplot(df)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/f060248e-e05c-4f49-a4b9-b557eac32db5)

~~~
sns.displot(x ="Glucose", data = df)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/dea09161-d891-42b8-be03-79f9784a77cc)

~~~
sns.displot(x ="BloodPressure", data = df)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/aea19133-242d-476a-b710-52240f23e8a5)

~~~
sns.displot(x ="BMI", data = df)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/fcebf125-c523-41cd-883a-3972fae7df7b)

~~~
sns.displot(x ="DiabetesPedigreeFunction", data = df)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/989aeb27-4254-4347-8118-2209699e60c6)

~~~
sns.displot(x ="Age", data = df)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/ec6dcecf-bbf0-464f-970f-209f9eb224d7)

~~~
from google.colab import files
uploaded = files.upload()
~~~
~~~

df = pd.read_csv('employeesal.csv')
df
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/8f4afbf4-d1df-4b28-afc1-b66415e60e8e)

~~~
df.isnull().sum()
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/54c7e081-4594-421e-b8c2-194cd4d31ca2)

~~~
numeric_cols = df.select_dtypes(include=[int, float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/f23366c8-a088-49cf-a8ee-294151ea493d)

~~~
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
numeric_cols.dropna()
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/e262feed-1e0a-4d5f-88cb-36db3439b7e8)

~~~
sns.boxplot(numeric_cols)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/0921d611-d607-45ae-86c8-fe7dbaaed314)

~~~
sns.histplot(x = 'Experience_Years',data = numeric_cols)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/3ced5ad9-2084-4430-95b7-96d7cf311392)

~~~
sns.histplot(x = 'Age',data = numeric_cols)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/ac8adfc7-c4a3-4bf8-981a-1a0ff255f4a8)

~~~
sns.histplot(x = 'Salary',data = numeric_cols)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/bd12e0f5-8a03-4971-9c9c-3c60fe555a88)

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
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/20159690-6b6b-456c-b01f-33cd9a8d25d0)

~~~
df.dropna()
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/24c1efc0-4bca-466f-b5a6-2dbf82e482fb)

~~~
df.dtypes
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/6f9daa1b-e4fa-4fd6-9862-017e3c6e8e73)

~~~
numeric_cols = df.select_dtypes(include=[float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/9749bd24-82d2-49e6-b602-ed20ff7239b9)

~~~
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
~~~
~~~
sns.boxplot(numeric_cols)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/15e1fb17-6333-43fa-b9a8-b91cd0ae5236)

~~~
sns.histplot(x = 'Sales',data = numeric_cols)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/44b66a57-13a4-45a1-ae05-6e13b7d918a3)

~~~
sns.countplot(x="Postal Code", data=numeric_cols)
~~~
![image](https://github.com/Kulaganachi/Univariate_Analysis/assets/133641126/4fdf1c5e-e6de-48f1-baa6-b1b8bd8b7749)


## RESULT:
Thus we have read the given data and performed the univariate analysis with different types of plots.













