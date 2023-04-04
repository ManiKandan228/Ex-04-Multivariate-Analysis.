# Ex-04-Multivariate-Analysis

## AIM
To perform Multivariate EDA on the given data set.

## Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM:

### STEP 1
Import the built libraries required to perform EDA and outlier removal.

### STEP 2
Read the given csv file

### STEP 3
Convert the file into a dataframe and get information of the data.

### STEP 4
Return the objects containing counts of unique values using (value_counts()).

### STEP 5
Plot the counts in the form of Histogram or Bar Graph.

### STEP 6
Use seaborn the bar graph comparison of data can be viewed.

### STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

### STEP 8
Save the final data set into the file

## PROGRAM
```
Name : MANIKANDAN P
Register Number : 212221040099

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from google.colab import files
uploaded = files.upload()
df = pd.read_csv("SuperStore.csv")
df
df.info()
df.describe()
df.isnull().sum()
df['Sales'] = df["Sales"].fillna(df['Sales'].mode()[0])
df.isnull().sum()
df.dtypes
sns.scatterplot(df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
df.info()
states=df.loc[:,["Postal Code","Sales"]]
states=states.groupby(by=["Postal Code"]).sum().sort_values(by="Sales")
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("Postal Code")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["Segment","Sales"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("Segment")
plt.ylabel=("Sales")
plt.show()
df.corr()
sns.heatmap(df.corr(),annot=True)
```

## OUTPUT

### DATA
![Data](https://user-images.githubusercontent.com/119160414/229297575-90650ceb-df98-4c53-a9c5-ce94aec256e0.png)

### DATA INFORMATION
![Data information](https://user-images.githubusercontent.com/119160414/229297594-2243bb7b-ad60-442d-bd08-b386a437048b.png)

### DATA DESCRIBE
![Data describe](https://user-images.githubusercontent.com/119160414/229297623-1831d78b-b01e-4e36-80a9-1a06130e546f.png)

### Checking the null values and Cleaning it
![Null sum](https://user-images.githubusercontent.com/119160414/229297657-f6e1a6b1-fcb6-4b96-95ee-89a6c80c6948.png)

![null 2](https://user-images.githubusercontent.com/119160414/229297669-1bde000c-1fbe-4311-bab9-e1a8cb6733f2.png)


### DATA TYPES
![datatype](https://user-images.githubusercontent.com/119160414/229297697-1eab71a0-9787-44b3-aa0f-5134d45940dc.png)

### SCATTERPLOT
![scatterplot](https://user-images.githubusercontent.com/119160414/229297717-73281f7d-58cf-4396-af99-827fd92ca9ee.png)

### BARPLOT
![Barplot](https://user-images.githubusercontent.com/119160414/229297754-a539b45c-01b2-4218-8a08-f217658f0590.png)

![barplot2](https://user-images.githubusercontent.com/119160414/229297764-f85fa1cb-0a83-44e7-96af-2691a747fed5.png)

![barplot3](https://user-images.githubusercontent.com/119160414/229297768-92a372df-a7cb-4198-9579-25b60c17ce75.png)

### CORRELATION COEFFICIENT INTERPRETATION
![correlation](https://user-images.githubusercontent.com/119160414/229297794-bf1cf5be-bb10-4a8a-ab30-29d1e89b223d.png)


### HEATMAP
![Heatmap](https://user-images.githubusercontent.com/119160414/229297824-2bdccb06-43c3-4946-9a2d-113895f65c6a.png)

## RESULT
Thus we have read the given data and performed the multivariate analysis with different types of
plots.
