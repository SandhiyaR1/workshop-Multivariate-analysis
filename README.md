# workshop-Multivariate-analysis
# AIM:
To perform Bivariate/Multivariate Analysis for the given data set.

# ALGORITHM:
### Step1 
Read the given data.
### Step2
Get information from the data.
### Step3
Perform the Multivariate Analysis.
### Step4
Save the cleaned data.

# PROGRAM:

DEVELOPED BY:Sandhiya R

REGISTRATION NUMBER: 212222230129
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
datas=pd.read_excel(r"/content/FlightInformation.xlsx")
df=pd.DataFrame(datas)
df
df.info()
df.head()
df.isnull().sum()
#Data cleaning
df['Route']=df['Route'].fillna(df['Route'].mode()[0])
df['Total_Stops']=df['Total_Stops'].fillna(df['Total_Stops'].mode()[0])
df.isnull().sum()
#NUMERICAL AND NUMERICAL
sns.scatterplot(x=df['Destination'],y=df['Price'])
sns.scatterplot(x=df['Destination'],y=df['Total_Stops'])
#NUMERICAL AND CATEGORICAL
sns.barplot(x=df["Source"],y=df["Price"],data=df)
sns.barplot(x=df['Source'],y=df['Price'],hue=df['Destination'])
DEST=df.loc[:,["Destination","Price"]]
DEST=DEST.groupby(by=["Destination"]).sum().sort_values(by="Price")
plt.figure(figsize=(7,7))
sns.barplot(x=airline.index,y="Price",data=DEST)
plt.xticks(rotation = 90)
plt.xlabel=("DESTINATION")
plt.ylabel=("PRICE")
plt.show()
sns.boxplot(x=df['Price'],y=df['Duration'])
sns.displot(df, x="Source", hue="Airline")
#MULTIVARIATE ANALYSIS 
df.corr()
sns.heatmap(df.corr(),annot=True)
```
# OUTPUT:
### df.head()
![image](https://user-images.githubusercontent.com/113497571/230104195-0fd17564-31ba-45c9-b1a9-cdb625b99900.png)
### df.isnull().sum()
![image](https://user-images.githubusercontent.com/113497571/230104640-05592722-4ee8-4829-8f03-2bdd21d8241e.png)
### After cleaning
###  df.isnull().sum()
![image](https://user-images.githubusercontent.com/113497571/230104913-eac32c42-183d-43c0-beac-66d26526f9a0.png)
### Numerical & Numerical
### scatter plot
![image](https://user-images.githubusercontent.com/113497571/230105301-c7e5e569-a2ef-4bcc-8fac-d688c9577071.png)
![image](https://user-images.githubusercontent.com/113497571/230105336-59dc0ab0-e377-4ba0-b736-db29c71c0866.png)
# Numerical & Categorical
### Barplot
![image](https://user-images.githubusercontent.com/113497571/230114797-d96fe112-c82f-4cc7-8f3e-c51756b179ef.png)
![image](https://user-images.githubusercontent.com/113497571/230114851-3841a22f-3ef3-41f2-bf78-9b2e4989b962.png)
![image](https://user-images.githubusercontent.com/113497571/230114892-8cf3ad91-ca89-4fe5-951b-829d42e9ff99.png)
### Boxplot
![image](https://user-images.githubusercontent.com/113497571/230115085-742c37fe-df90-44ca-bf26-50516ea248b0.png)
### Distplot
![image](https://user-images.githubusercontent.com/113497571/230115216-940ff999-5e6f-4876-8d9e-bb0dda82ffff.png)
# Multivariate Analysis
### Heatmap
![image](https://user-images.githubusercontent.com/113497571/230115503-2b6dc897-1826-4291-9178-d399c1129435.png)
# RESULT
Thus the Bivariate/Multivariate Analysis for the given data set is executed successfully.





