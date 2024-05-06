![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/b813a13e-aa28-4c33-b243-4276ce5afdcc)![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/4fb3d065-a893-4cc9-868c-aeb016cfa6e9)# EX:6 DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```
import seaborn as sns
import matplotlib.pyplot as plt
```

### 1.Line Plot
```
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]

sns.lineplot(x=x, y=y)
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/c232851c-7936-4af2-8337-abc58099dce1)

```
df = sns.load_dataset("tips")
df
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/edbd8ed6-81f1-4608-b332-7afe350d5ba2)

```
sns.lineplot(x="total_bill", y="tip", data=df, hue="sex", linestyle="solid", legend="auto")
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/6c688ed5-5ed1-450a-af8c-f3c1d9c889d8)


### 2.Multi Line Plot
```
x=[1,2,3,4,5]
y1=[3,5,2,6,1]
y2=[1,6,4,3,8]
y3=[5,2,7,1,4]

sns.lineplot(x=x,y=y1)
sns.lineplot(x=x,y=y2)
sns.lineplot(x=x,y=y3)
plt.xlabel("X Label")
plt.ylabel("Y Label")
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/c284b5ce-ac06-419d-ba83-58016c830989)


## TO VISUALIZE RELATIONSHIPS
### 1.Bar Chart
```
import seaborn as sns
import matplotlib.pyplot as plt
tips = sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()

plt.figure(figsize=(8,6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')

plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/5a73105a-a810-44f1-87ba-b5c3d6b38680)

```
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip = tips.groupby('time')['tip'].mean()

p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip', width=0.4)

plt.xlabel('Time of the Day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Time of Day')
plt.legend()
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/88e69181-f269-4caf-8585-081405c62bd8)

```
years = range(2000, 2012)
apples = [0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896 ]

plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/934eca71-26f6-4b0b-a08a-ec5542827db9)

```
dt = sns.load_dataset('tips')
sns.barplot(x = 'day', y = 'total_bill', hue = 'sex', data = dt, palette = 'Set1')

plt.xlabel('Day of the Week')
plt.ylabel('Total Bill')
plt.title('Total Bill by Day and Gender')
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/e342e20b-f3fe-4826-a70c-921fc5050d8e)

```
import pandas as pd
tit = pd.read_csv("titanic_dataset.csv")
tit
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/00b6369e-7e38-4586-9ad5-9e240985992a)

```
plt.figure(figsize = (8,5))
sns.barplot(x = 'Embarked', y = 'Fare', data=tit, palette = 'rainbow')
plt.title("Fare of Passenger by Embarked Town")
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/ddff93da-2177-4b2c-9b06-608c244b0a6f)

```
plt.figure(figsize=(8,5))
sns.barplot(x = 'Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/b897c111-0650-4683-beac-8da2c408fb4d)


### 2.Scatter Plot
```
tips = sns.load_dataset('tips')
sns.scatterplot(x = 'total_bill', y='tip', hue='sex', data=tips)

plt.title('Total Bill')
plt.xlabel('Tip Amount')
plt.ylabel('Scatter Plot of Total Bill vs. Tip Amount')
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/3a89fefe-b947-4d1f-ba10-116998ee31bc)

### 3.Bubble Chart
```
sns.scatterplot(x="Age", y="Fare", size="Pclass", data=df, sizes=(30, 200))
plt.title('Bubble Chart of Age vs Fare, Size by Passenger Class')
plt.show()
```
![6-5](https://github.com/Divya110205/EXNO-6-DS/assets/119404855/bd9c1f59-b33b-4869-aa5a-0ee876a7c8ab)

## TO CAPTURE DISTRIBUTIONS
```
import seaborn as sns
import numpy as np
import pandas as pd

np.random.seed(1)
num_var = np.random.randn(1000)
num_var = pd.Series(num_var, name= "Numerical Variable")
num_var
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/fb971ed0-1c4c-43cd-a692-93ff2d626c00)

### 1.Histogram
```
sns.histplot(data = num_var, kde = True)
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/a64b1de8-4d4c-4113-828f-2eca30d43a28)

```
df=pd.read_csv('titanic_dataset.csv')
sns.histplot(data = df, x="Pclass", hue="Survived", kde=True)
```
```
sns.boxplot(x='Pclass',y='Age',data=df,palette='rainbow')
plt.title("Age By Passenger Class")
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/f4d38c20-f93e-4ec0-a0d1-4cd8138e674e)


### 2.Box Plot
```
import seaborn as sns
import pandas as pd
tips = sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips['total_bill'], hue=tips['sex'])
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/e196190a-3628-4121-95b6-8cd0b70e2d21)

```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops = {"facecolor" : "lightblue", "edgecolor" : "darkblue"},
            whiskerprops = {"color" : "black", "linestyle" : "--", "linewidth" : 1.5}, capprops = {"color" : "black", "linestyle" : "--", "linewidth" : 1.5})
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/ee906dff-d946-4a92-a46b-9cbd6b60275f)

```
sns.boxplot(x = 'Pclass', y='Age', data=df, palette='rainbow')
plt.title("Age by Passenger Class, Titanic")
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/a288e051-18cb-466c-be06-0d3889ad93ce)



### 3.Violin Plot
```
sns.violinplot(x = "day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette = 'Set1', inner = "quartile")

plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/25308afd-ec51-4d88-8554-a2a92d2a3cf3)

```
import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x ='day', y ='tip', data = tip)
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/9f731a19-a0df-4c30-8a69-5c0a2ced2bc8)

```
import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x = tip["total_bill"])
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/a0377b82-172b-4ca9-b626-58b17f7ae104)

```
import seaborn as sns
sns.set(style = "whitegrid")
tips = sns.load_dataset("tips")
sns.violinplot(x = 'tip', y = 'day', data = tip)
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/9f7d39d8-20e1-45c0-9f73-3ebe2b641d5c)


### 4.Density Plot
```
sns.kdeplot(data=df, shade=True)
plt.title('Density Plot of Passenger Ages')
plt.show()
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/e6fdfa54-aa19-4d02-b9e3-ff6a9c021333)

```
import seaborn as sns
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

mart = pd.read_csv("supermarket.csv")
```
```
mart = mart[['Gender', 'Payment', 'Unit price', 'Quantity', 'Total', 'gross income']]
mart.head(10)
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/81f6a256-fce3-42ef-b7df-6e0c025c43c6)

```
sns.kdeplot(data = mart, x = 'Total')
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/fd04bc1e-db63-4937-bcb6-d8636b35b26b)

```
sns.kdeplot(data = mart, x = "Unit price")
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/9af31847-a3a5-494d-a5a4-81f1af403611)

```
sns.kdeplot(data=mart)
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/cbc68ea3-a97e-4472-a577-9a8e9d1a80d5)

```
sns.kdeplot(data=mart, x='Total', hue='Payment', multiple= 'stack')
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/bf0c3dd0-3435-408f-8d73-49aab240b59f)

```
sns.kdeplot(data=mart, x='Total', hue='Payment', multiple='stack', linewidth=5, palette='Dark2', alpha=0.5)
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/1062e7c0-4ba2-48de-9e43-d700668ec0e2)

```
sns.kdeplot(data=mart, x='Unit price', y='gross income')
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/5d2f1067-fc24-410d-83b6-41979f1e6d44)


### 5.Heatmap
```
data = np.random.randint(low = 1, high = 100, size = (10, 10))
print("The data to be plotted.\n")
print(data)
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/51efc57a-9e41-4438-a500-4d198af38101)

```
numeric_df = df.select_dtypes(include=['float64', 'int64'])
corr_matrix = numeric_df.corr()
sns.heatmap(corr_matrix, annot=True, cmap='coolwarm')
plt.title('Heatmap of Titanic Dataset')
plt.show()
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/1dbf20d4-d7bf-42a8-8bc7-13737991d3aa)

```
hm = sns.heatmap(data = data, annot=True)
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/3b492335-c15d-42da-9d75-5a2efb6d9764)

```
hm = sns.heatmap(data = data)
```
![image](https://github.com/Prasannalakshmiganesan/EXNO-6-DS/assets/118610231/3af61488-27b6-43e9-be26-490208198f4b)


# Result:
  Thus, the Data Visualization using seaborn python library for the given data is implemented successfully
