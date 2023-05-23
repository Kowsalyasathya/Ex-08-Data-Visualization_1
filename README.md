# Ex-09-Data-Visualization-

## AIM:
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM:
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE:
```
NAME:KOWSALYA M
REGISTER NUMBER:212222230069

Data Preprocessing

import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
df = sns.load_dataset("tips")
print(df)

df.isnull().sum()

Handling Outliers
plt.figure(figsize=(8,8))
plt.title("Data with Outliers")
df.boxplot()
plt.show()

Removing Outliers
plt.figure(figsize=(8,8))
cols = ['size','tip','total_bill']
Q1 = df[cols].quantile(0.25)
Q3 = df[cols].quantile(0.75)
IQR = Q3 - Q1
df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]
plt.title("Dataset after removing outliers")
df.boxplot()
plt.show()

1) Which day of the week has the highest total bill amount?
sns.barplot(x=df['day'], y=df['total_bill'], hue=df['day'])
plt.legend(loc="center")
plt.title("Highest Total Bill Amount by day of the week")
plt.show()

2) What is the average tip amount given by smokers and non-smokers?
sns.boxplot(x=df['smoker'], y=df['tip'], hue=df['smoker'])
plt.title("Average Tip Amount given by smokers and non-smokers")

3) How does the tip percentage vary based on the size of the dining party?
df["tip_percent"] = df["tip"] / df["total_bill"]
sns.scatterplot(x=df['size'],y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")

4) Which gender tends to leave higher tips?
sns.boxplot(x=df['sex'], y=df['tip'],hue=df['sex'])
plt.title("Tips based on gender")

5) Is there any relationship between the total bill amount and the day of the week?
sns.scatterplot(x=df['day'],y=df['total_bill'],hue=df['day'])
plt.legend(loc="best")
plt.title("Total bill amount by day of the week")

6) How does the distribution of total bill amounts vary across different time periods (lunch vs. dinner)?
sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")
plt.title("Distribution of Total Bill Amounts by Time of Day")
plt.show()

7) Which dining party size group tends to have the highest average total bill amount?
sns.barplot(x=df['size'],y=df['total_bill'],hue=df['size'])
plt.title("Average Total Bill Amount by Dining Party Size")
plt.show()

8) What is the distribution of tip amounts for each day of the week?
sns.boxplot(x="day", y="tip", data=df)
plt.title("Tip Amount by Day of Week")
plt.show()

9) How does the tip amount vary based on the type of service (lunch vs. dinner)?
sns.violinplot(x="time", y="tip", data=df)
plt.title("Tip Amount by Time of Day")
plt.show()

10) Is there any correlation between the total bill amount and the tip amount?
sns.scatterplot(x="total_bill", y="tip", data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()

```
# OUPUT:
![9 1](https://github.com/Kowsalyasathya/Ex-08-Data-Visualization_1/assets/118671457/326d6dae-e0e3-43c7-b34c-acbb050c42ca)
![9 2](https://github.com/Kowsalyasathya/Ex-08-Data-Visualization_1/assets/118671457/f345c9b3-d592-4db6-bd85-6683e81ec110)
![9 3](https://github.com/Kowsalyasathya/Ex-08-Data-Visualization_1/assets/118671457/c96c0792-756b-4bdd-91df-49ba577b2003)
![9 4](https://github.com/Kowsalyasathya/Ex-08-Data-Visualization_1/assets/118671457/95d05b50-10f8-4ebe-8c21-9b70a42f61c9)
![9 5](https://github.com/Kowsalyasathya/Ex-08-Data-Visualization_1/assets/118671457/40347d79-db63-4c19-9299-082a30e0e979)
![9 6](https://github.com/Kowsalyasathya/Ex-08-Data-Visualization_1/assets/118671457/962194ef-2759-4f9c-a9e2-dbb2bec621e6)

![9 7](https://github.com/Kowsalyasathya/Ex-08-Data-Visualization_1/assets/118671457/b3c70f1b-7924-4474-8b7a-13813e685350)
![9 8](https://github.com/Kowsalyasathya/Ex-08-Data-Visualization_1/assets/118671457/eb13e15c-dba8-4a4b-bf25-b1e135518dbb)
![9 9](https://github.com/Kowsalyasathya/Ex-08-Data-Visualization_1/assets/118671457/7eac7f8e-be8d-4843-890b-6ba3c7e77de9)
![9 10](https://github.com/Kowsalyasathya/Ex-08-Data-Visualization_1/assets/118671457/4ef296b2-009f-45a9-8786-12190c971045)

## RESULT:

Thus the Data Visualization method is performed to the given data and to predict the outcome for the given questions.

