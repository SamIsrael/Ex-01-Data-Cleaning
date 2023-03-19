# Ex-01_DS_Data_Cleansing
# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# ALGORITHM
## STEP 1
Read the given Data

## STEP 2
Get the information about the data

## STEP 3
Remove the null values from the data

## STEP 4
Save the Clean data to the file

# CODE
```python

import pandas as pd

df = pd.read_csv('Data_set.csv')
print(df)
print(df.info())
print(df.isnull())
print(df.isnull().sum())


df['show_name'] = df["show_name"].fillna(df['show_name'].mode()[0])
df.dropna()
df.dropna(axis=0)
df['rating'] = df['rating'].fillna(value=df['rating'].mean())
df['watchers'] = df['watchers'].fillna(value=df['watchers'].mean())
df['current_overall_rank'] = df['current_overall_rank'].fillna(df['current_overall_rank'].median())
df['aired_on'] = df['aired_on'].fillna(method='ffill')
df['original_network'] = df['original_network'].fillna(method='bfill')
print("\n\n*****DATA AFTER CLEANING*****\n\n")
print(df)
print(df.isnull().sum())

```
# OUPUT
![image](./Screenshot%20from%202023-03-19%2020-54-21.png)
![image](./Screenshot%20from%202023-03-19%2020-54-29.png)
![image](./Screenshot%20from%202023-03-19%2020-54-40.png)
