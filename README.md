# Ex-01_DS_Data_Cleansing


## AIM
To read the given data and perform data cleaning and save the cleaned data to a file. 

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. 
Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information. 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Get the information about the data
### STEP 3
Remove the null values from the data
### STEP 4
Save the Clean data to the file

# CODE and OUTPUT
# Data Cleaning

```
import pandas as pd
data=pd.read_csv("/content/Data_set.csv")
data.head(7)
```
![image](https://github.com/user-attachments/assets/340fec3c-ed7f-49b2-a620-4bb1f54d0e23)
```
data.tail()
```
![image](https://github.com/user-attachments/assets/7a0df7fa-3847-4d71-8720-7df97fb06919)
```
data.isnull()
```
![image](https://github.com/user-attachments/assets/b9945143-b38b-448b-9a0f-debe6b861404)
```
data.fillna(5)
```
![image](https://github.com/user-attachments/assets/85848162-df9c-4e0a-a97d-8d9027595341)
```
data.notnull()
```
![image](https://github.com/user-attachments/assets/d8dd24b5-0c82-4ad3-8fb5-87f19dde86c9)

```
data.dropna(axis=1)
```
![image](https://github.com/user-attachments/assets/bc18cc5e-f809-4fd0-b491-dbe7019e5fbe)
```
data.dropna(axis=0)
```
![image](https://github.com/user-attachments/assets/54817f43-a886-46f2-b31b-f05627748557)
```
data.shape
```
![image](https://github.com/user-attachments/assets/dbe46573-6afc-4be1-9bee-e162be348670)
```
data.describe()
```
![image](https://github.com/user-attachments/assets/3a775e04-4d7e-4721-8051-e3a3656d43df)
```
data.fillna(method='ffill')
```
![image](https://github.com/user-attachments/assets/41a08eb4-06c1-482c-94f1-0b12df835a87)
```
data.fillna(method='bfill')
```
![image](https://github.com/user-attachments/assets/1e48c6fc-1e65-477e-b9d8-1fc4820c265e)
```
data.isnull().sum()
```
![image](https://github.com/user-attachments/assets/4d2055cc-6519-418b-ac2a-db8f4d2087c9)
```
data.isnull().any()
```
![image](https://github.com/user-attachments/assets/f7e8d8d4-3680-4499-a84e-58f4357cd652)
# IQR(inter quartile range)
```
ir=pd.read_csv('/content/iris.csv')
ir
```
![image](https://github.com/user-attachments/assets/56a0d022-8edd-4080-9951-389345aaf643)
```
ir.describe()
```
![image](https://github.com/user-attachments/assets/76a7d4e1-8866-456a-ab63-39f5ea15f7f2)
```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```
![image](https://github.com/user-attachments/assets/bdf412a2-5d06-443f-8140-67734cb9b2b9)
```
q1=ir.sepal_width.quantile(0.25)
q3=ir.sepal_width.quantile(0.75)
iq=q3-q1
print(q3)
```
![image](https://github.com/user-attachments/assets/bed3a35b-c9e4-47b4-9a50-32ac9de6e6be)
```
delid=ir[~((ir.sepal_width<(q1-1.5*iq))|(ir.sepal_width>(q3+1.5*iq)))]
print(delid)
```
![image](https://github.com/user-attachments/assets/809f9c10-41a9-45f6-89f1-2cafdaf0d5da)
```
rid=ir[((ir.sepal_width<(q1-1.5*iq))|(ir.sepal_width>(q3+1.5*iq)))]
rid['sepal_width']
```
![image](https://github.com/user-attachments/assets/e80c9c7f-1689-4c77-9c35-a52da7d90978)
```
import seaborn as sns
sns.boxplot(x='sepal_width',data=delid)

```
![image](https://github.com/user-attachments/assets/d4107477-d920-497f-b199-28c17f15694c)

# z-score
```
import pandas as pd
import scipy.stats as stats
import numpy as np
hp=pd.read_csv("/content/heights.csv")
hp
```
![image](https://github.com/user-attachments/assets/5a7a1872-8ae2-46ba-b462-701718474fe3)
```
z=np.abs(stats.zscore(hp["height"]))
z
```
![image](https://github.com/user-attachments/assets/203ab38b-e07a-4c9f-9039-b43268238c81)

```
hp1=hp[z<3]
hp1
```
![image](https://github.com/user-attachments/assets/dda80ae9-7c99-4754-85b7-114d80ca960d)














