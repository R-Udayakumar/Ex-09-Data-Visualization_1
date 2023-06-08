### Ex-09-Data-Visualization-

### AIM

To Perform Data Visualization on a complex dataset and save the data to a file.

### Explanation

Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

### ALGORITHM

### STEP 1

Read the given Data

### STEP 2

Clean the Data Set using Data Cleaning Process

### STEP 3

Apply Feature generation and selection techniques to all the features of the data set

### STEP 4

Apply data visualization techniques to identify the patterns of the data.

### CODE
```python
# Developed by Udayakumar R
# Reg no: 212222230163

import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
df = sns.load_dataset("tips")
df.head()
df.isnull().sum()

plt.figure(figsize=(8,8))
plt.title("Data with Outliers")
df.boxplot()
plt.show()

plt.figure(figsize=(8,8))
cols = ['size','tip','total_bill']
Q1 = df[cols].quantile(0.25)
Q3 = df[cols].quantile(0.75)
IQR = Q3 - Q1
df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]
plt.title("Dataset after removing outliers")
df.boxplot()
plt.show()

# 1) 
sns.barplot(x=df['day'], y=df['total_bill'], hue=df['day'])
plt.legend(loc="center")
plt.title("Highest Total Bill Amount by day of the week")
plt.show()

# 2)
sns.boxplot(x=df['smoker'], y=df['tip'], hue=df['smoker'])
plt.title("Average Tip Amount given by smokers and non-smokers")

# 3) 
df["tip_percent"] = df["tip"] / df["total_bill"]
sns.scatterplot(x=df['size'],y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")

# 4) 
sns.boxplot(x=df['sex'], y=df['tip'],hue=df['sex'])
plt.title("Tips based on gender")

# 5)
sns.scatterplot(x=df['day'],y=df['total_bill'],hue=df['day'])
plt.legend(loc="best")
plt.title("Total bill amount by day of the week")

# 6)
sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")
plt.title("Distribution of Total Bill Amounts by Time of Day")
plt.show()

# 7)
sns.barplot(x=df['size'],y=df['total_bill'],hue=df['size'])
plt.title("Average Total Bill Amount by Dining Party Size")
plt.show()

# 8) 
sns.boxplot(x="day", y="tip", data=df)
plt.title("Tip Amount by Day of Week")
plt.show()

# 9)
sns.violinplot(x="time", y="tip", data=df)
plt.title("Tip Amount by Time of Day")
plt.show()

# 10)
sns.scatterplot(x="total_bill", y="tip", data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()
```

### OUTPUT:

### DATA PREPROCESSING

![image](https://github.com/R-Udayakumar/Ex-09-Data-Visualization_1/assets/118708024/08b357a7-7e4c-4bc2-9a48-19a8b596e1f4)

![image](https://github.com/R-Udayakumar/Ex-09-Data-Visualization_1/assets/118708024/f956414a-7889-484e-952f-825e69070d70)

![image](https://github.com/R-Udayakumar/Ex-09-Data-Visualization_1/assets/118708024/efa36570-0f11-4179-9e01-7a739b9ca73e)

![image](https://github.com/R-Udayakumar/Ex-09-Data-Visualization_1/assets/118708024/7452769a-27aa-4208-8fa0-bcfc23443962)

![image](https://github.com/R-Udayakumar/Ex-09-Data-Visualization_1/assets/118708024/7fa43806-78f6-4123-af38-8730216d5f78)

![image](https://github.com/R-Udayakumar/Ex-09-Data-Visualization_1/assets/118708024/e7fc4eb2-2c5c-4d19-87c0-2ed278ab8f84)

![image](https://github.com/R-Udayakumar/Ex-09-Data-Visualization_1/assets/118708024/7f3a9d99-9050-4d5a-bc46-d046503a77cd)

![image](https://github.com/R-Udayakumar/Ex-09-Data-Visualization_1/assets/118708024/0bd15eb9-d6c6-45c3-8488-25e5e35b35aa)

![image](https://github.com/R-Udayakumar/Ex-09-Data-Visualization_1/assets/118708024/5ed71609-626b-4af9-95ae-3c748f95aca7)

![image](https://github.com/R-Udayakumar/Ex-09-Data-Visualization_1/assets/118708024/74a989ba-2004-4469-8060-0cc65698f540)

![image](https://github.com/R-Udayakumar/Ex-09-Data-Visualization_1/assets/118708024/f5b8dc7b-f06a-4821-b2c7-c20918d1eb5f)

![image](https://github.com/R-Udayakumar/Ex-09-Data-Visualization_1/assets/118708024/421f98b3-f20b-4a3c-b63e-697b0073b39e)

![image](https://github.com/R-Udayakumar/Ex-09-Data-Visualization_1/assets/118708024/6e5a2ad2-0b3a-44d5-a18d-7ee8d63296ce)

![image](https://github.com/R-Udayakumar/Ex-09-Data-Visualization_1/assets/118708024/961f2217-ba31-4adf-8078-c5050fc4cce2)

### RESULT

Thus the Data Visualization method is performed to the given data and to predict the outcome for the given questions. 
