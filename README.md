# ODD2023-Datascience-Ex-04
## DATE:

### AIM:
To perform Multivariate EDA on the given data set.
### EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
### ALGORITHM:
### STEP 1:
Import the built libraries required to perform EDA and outlier removal.
### STEP 2:
Read the given csv file
### STEP 3:
Convert the file into a dataframe and get information of the data.
### STEP 4 :
Return the objects containing counts of unique values using (value_counts()).
### STEP 5 :
Plot the counts in the form of Histogram or Bar Graph.
### STEP 6:
Use seaborn the bar graph comparison of data can be viewed.
### STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr()

### STEP 8:
Save the final data set into the file.

###  PROGRAM:
```
Name : HARINI V
Register Number : 212222230044
```

### SuperStore.csv file:
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("/content/SuperStore (1).csv")
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

## diabetes.csv file:

```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("/content/diabetes.csv")
df
df.describe()
df.info
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
### OUTPUT:
 
### SUPERSTORE:

DATA FRAME OF SUPERSTORE:

![273436811-04da1d1e-4305-4abf-825d-effe43521a9f](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/1fa8fce4-890d-4bff-a44b-b8c196b4a3f5)

Data information

![273436436-c443883f-8cf6-4f5f-b4ee-eef401730a59](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/628add2e-c7f1-4d86-b4a3-b1d37c63dbcd)

Data describing:

![273436443-51b07f4d-77eb-4482-a5c8-fe68ec112bc2](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/e2906abb-ef3d-4392-838d-3a4f3a46cc6e)

Sum of null values
![273436449-f0958e9d-36fe-4745-93cf-3885d67e855b](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/274a4c56-10ce-4fbe-b13c-998fbe78a3bd)


After removing null values:
![273436456-c29779d4-e3d8-4391-a59a-b65b8cc25e9f](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/05a5956f-bd7c-45b3-9b48-6d63772c14b2)

Scatter plot:

![273436476-cd55d233-5f25-4451-9eac-1270557c5c14](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/fb2790de-ea7f-446d-9d23-a029b9bc669d)

Bar plot:
![273436479-a1ba9121-6cc4-4a13-93cc-c884491218dd](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/edc8ab2e-8041-419e-9cb1-9fd3ea431d16)

![273436485-1fb3fb81-f2a7-4c34-9cc5-84dc2d8a9501](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/7900fa42-ce29-482e-909b-04637967ce6f)

Box plot:
![273436511-92fa18b4-46e9-4e75-abbf-208ea3dea94c](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/a97b666a-05bc-49fc-805e-aa6111cd12a3)

Dist plot:

![273436520-6582fd54-083b-482a-9670-40ce01d38e7f](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/afff1554-35d8-4d5d-a5c6-2517e41e03e0)

Correlation coefficient interpretation:

![273436530-80d97153-1912-40ca-9a7c-875c63ae7486](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/64551be3-ca93-4afe-b2b2-94a7485230c5)
Heat map:

![273436537-4204da31-bbfc-4051-842a-bd3b8e0a3cbb](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/a1479ec5-4437-4701-a1f0-37337d78f844)


### DIABETES:

DATA FRAME FOR DIABETES:

![273436553-d4d5c50b-015f-4d2a-bb29-39370301a9ce](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/e1f804a2-c461-4e83-82f9-3b44fe285003)

Data information1:

![273436559-e267215f-0108-4655-8a4e-3e3e6117f257](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/eaaf431f-1e9b-4c88-ac85-2371726ce784)

Data describing:

![273436564-13ff73a9-97ea-485f-a799-45edb43d6e6a](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/8b794e77-d97f-4fcf-b71b-388ca16df7a4)


Sum of null values:


![273436571-c1e2954b-2fe8-4e63-935f-fcf168d03e20](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/21ce1994-e1ae-4600-811d-e524a35ecbc8)


Scatter plot:
![273436579-7e7e1712-2305-4cb4-afcb-ea4f42e0c9a7](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/04db704b-8eaf-4c53-9f1e-a2fe92d3acaa)


![273436583-bb3781f1-5fa4-4194-b16c-03ba3a662fb4](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/cbabb3c2-1b2a-4190-a0d6-b856b7a1f50a)

Bar plot:


![273436590-c93a6716-2d38-4268-aeae-b3fee90409fd](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/e167acdc-b6b0-4f80-8792-2c96b297cab6)


![273436599-10b80b0f-af9a-4d60-8284-22d682c724e3](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/8bedfb5b-d600-4045-bf25-117c25128785)

Box plot:

![273436607-aaf4bb9d-1541-4ad0-b5ef-a389d7bd0adb](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/dae4ddbc-3786-45b9-a9fe-fff363f05765)
Dist plot:

![273436614-a8b71f2b-e474-4f80-a354-8e6e1aa15062](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/a66e4511-fbe9-45a0-8c1d-237aba723673)

correlation coefficient interpretation:
![273436624-5b89025c-0179-4741-934c-6ef20fe8e3df](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/31eff66e-3575-4d6c-99d7-3ee6ed5d4c98)


Heat map:



![273436634-71fa8088-79a1-4896-853b-cccb9a47d230](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-04/assets/113497037/52141eca-21e2-47ea-95a7-ba64d1ac8353)


### RESULT::


Thus we have read the given data and performed the multivariate analysis with different types of plots.
















