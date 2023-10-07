# ODD2023-Datascience-Ex-04
## AIM:
To perform Multivariate EDA on the given data set.

## EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM:
### STEP 1:
Import the built libraries required to perform EDA and outlier removal.
### STEP 2:
Read the given csv file
### STEP 3:
Convert the file into a dataframe and get information of the data.
### STEP 4:
Return the objects containing counts of unique values using (value_counts()).
### STEP 5:
Plot the counts in the form of Histogram or Bar Graph.
### STEP 6:
Use seaborn the bar graph comparison of data can be viewed.
### STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr()
### STEP 8:
Save the final data set into the file.

## PROGRAM:
```
Developed by:VASUNDRA SRI R
Register no:212222230168
```
## SuperStore.csv:
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("/content/SuperStore.csv")
df=pd.DataFrame(data)
df.head()
df.info()
df.describe()
df.isnull().sum()
df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()

sns.scatterplot(x=df['Region'],y=df['Sales'])

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=states.index,y="Sales",data=states)

states=df.loc[:,["Ship Mode","Row ID"]]
states=states.groupby(by=["Ship Mode"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SHIP MODE")
plt.ylabel=("ROW ID")
plt.show()

sns.boxplot(x=df['Ship Date'],y=df['Sales'])
sns.displot(df, x="Region", hue="Category")
df.corr()
sns.heatmap(df.corr(),annot=True)
```
## Diabetes.csv:
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("/content/diabetes.csv")
df
df.info()
df.describe()
df.isnull().sum()

sns.scatterplot(x=df['Glucose'],y=df['BloodPressure'])

sns.scatterplot(x=df['Glucose'], y=df['BloodPressure'], hue=df['Outcome'])

Age=df.loc[:,["Age","BMI"]]
Age=Age.groupby(by=["Age"]).sum().sort_values(by="BMI")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=Age.index,y="BMI",data=Age)

Age=df.loc[:,["BloodPressure","Glucose"]]
Age=Age.groupby(by=["BloodPressure"]).sum().sort_values(by="Glucose")
sns.barplot(x=Age.index,y="Glucose",data=Age)
plt.xticks(rotation = 90)
plt.xlabel=("BloodPressure")
plt.ylabel=("Glucose")
plt.show()

sns.boxplot(x=df['DiabetesPedigreeFunction'],y=df['Insulin'])

sns.displot(df, x="Glucose", hue="Outcome")

df.corr()

sns.heatmap(df.corr(),annot=True)
```
## OUTPUT:
## Data frame of SuperStore:
![dataframe](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/cb8c90b9-7659-4b5e-bdf1-c80cb9ae0f5e)

## Data information:
![infos](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/2c2e85ac-a4e2-4221-8f4a-5c714b743f4d)

## Data describing:
![describes](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/af0cbff2-8688-44e4-8326-07d5a3cafc3b)

## Sum of null values:
![iss](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/4fb61401-8eb3-4b27-9c1e-c3eed83802c2)

## After removing null values:
![nulls](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/27243d60-3689-49f6-8ca0-a13002c62323)

## Scatter plot:
![scatters](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/0ac3b392-4819-42c1-82d4-bacea0c22073)

## Bar plot:
![statess](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/40743103-97f6-47a9-950d-e95079d9eefb)
![plots](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/78d7d3f2-79a5-472b-9b82-c0a164131beb)

## Box plot:
![boxs](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/a34ee736-1707-4026-980d-e36535d56eb1)

## Dist plot:
![regions](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/bcc1a7d3-7819-4ea8-8a70-de3f01fc1d06)

## Correlation coefficient interpretation:
![corrs](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/08274322-35ab-47fd-8147-bb13c801de0b)

## Heat map:
![heats](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/74ff659d-7170-4d6e-8709-d1282c7b7793)

## Data frame for diabetes:
![dd](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/2e68bab0-be6b-4e48-bb93-1b2ce6dc6e1d)

## Data information:
![infod](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/45a7d3b4-38b7-4899-99c8-f01c690fe09e)

## Describing a data set:
![desd](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/26ab0a88-61fb-40f9-92e5-17ca3290b7ac)

## Sum of null values:
![dis](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/8928fbbe-020d-481e-8ee3-7b56086252f8)

## Scatter plot:
![ds](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/b033c479-92f0-4861-a1a0-b2f884f21e8c)
![ds1](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/ccc9b40b-2d9f-43b9-b7f6-7deb20727fbb)

## Bar plot:
![ds2](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/aed11ce6-0da7-4738-98f1-9caa639d4d20)
![ds3](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/1f406646-7c6a-4284-a72d-e2fae618b27c)

## Box plot:
![ds4](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/57aa6ccc-7009-4f23-81cc-eefb9af320df)

## Dist plot:
![ds5](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/d2ccde23-9d1b-430c-87c5-101004704abc)

## Correlation coefficient interpretation:
![ds6](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/2e070ffc-727d-4a0a-ad2e-23b87b79d610)

## Heat map:
![ds7](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-04/assets/119393983/654cfb1d-ce14-4b1c-ac55-74cb8c77c88c)

## RESULT:
Thus we have read the given data and performed the multivariate analysis with different types of plots.
