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



