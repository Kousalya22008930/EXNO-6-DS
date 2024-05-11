# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

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
## Line plot:
```
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]

sns.lineplot(x=x, y=y)
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/cafb8591-2bb3-4042-8b54-c0b23fadf21e)
```
df = sns.load_dataset("tips")
df
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/2d8f12d5-9dd4-4ec5-a53f-50e9b4bedb54)
```
sns.lineplot(x="total_bill", y="tip", data=df, hue="sex", linestyle="solid", legend="auto")
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/64cf9479-2912-4d23-80c8-e13e40787074)
### Multi Line Plot
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
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/c434661c-f396-4a65-8d78-a74f08b5efde)
### TO VISUALIZE RELATIONSHIPS
#### Bar Chart
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
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/409c3ca0-4894-40c7-b7c8-cdeb5a24b87d)
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
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/a9f442e4-4572-4999-aded-382c06e2ed83)
```
years = range(2000, 2012)
apples = [0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896 ]

plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/cb27c021-2cc0-485f-97b8-e15230ac5365)
```
dt = sns.load_dataset('tips')
sns.barplot(x = 'day', y = 'total_bill', hue = 'sex', data = dt, palette = 'Set1')

plt.xlabel('Day of the Week')
plt.ylabel('Total Bill')
plt.title('Total Bill by Day and Gender')
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/37ac4d6f-0ae7-401d-a46e-561f0ebff069)
```
import pandas as pd
tit = pd.read_csv("titanic_dataset.csv")
tit
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/a3b22429-a48f-485d-aaeb-e84b06531f56)

```
plt.figure(figsize = (8,5))
sns.barplot(x = 'Embarked', y = 'Fare', data=tit, palette = 'rainbow')
plt.title("Fare of Passenger by Embarked Town")
```

![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/dc02be89-49cd-450f-affb-0ea6daaddf42)
```
plt.figure(figsize=(8,5))
sns.barplot(x = 'Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/607126b3-f49d-444c-aeb5-bc2066f03818)
### Scatter plot
```
tips = sns.load_dataset('tips')
sns.scatterplot(x = 'total_bill', y='tip', hue='sex', data=tips)

plt.title('Total Bill')
plt.xlabel('Tip Amount')
plt.ylabel('Scatter Plot of Total Bill vs. Tip Amount')
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/c7f0d3e8-7c58-4fc7-9170-ea46b90f34c9)
### Bubble Chart
```
sns.scatterplot(x="Age", y="Fare", size="Pclass", data=df, sizes=(30, 200))
plt.title('Bubble Chart of Age vs Fare, Size by Passenger Class')
plt.show()
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/ea854b5e-1344-4137-9379-6c04e9142dbd)
### TO CAPTURE DISTRIBUTIONS
```
import seaborn as sns
import numpy as np
import pandas as pd

np.random.seed(1)
num_var = np.random.randn(1000)
num_var = pd.Series(num_var, name= "Numerical Variable")
num_var
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/c2f2b850-fabc-4104-9209-4d3d16366cfc)
### Histogram
```
sns.histplot(data = num_var, kde = True)
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/6caaf382-c75e-48b2-a238-e31c75757832)
```
sns.boxplot(x='Pclass',y='Age',data=df,palette='rainbow')
plt.title("Age By Passenger Class")
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/a48ef44b-2dc2-4e7c-b8a3-8075c416f0c0)

### Box Plot
```
import seaborn as sns
import pandas as pd
tips = sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips['total_bill'], hue=tips['sex'])
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/9dd9cf27-55b3-4941-b85d-efabcb84b84c)
```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops = {"facecolor" : "lightblue", "edgecolor" : "darkblue"},
            whiskerprops = {"color" : "black", "linestyle" : "--", "linewidth" : 1.5}, capprops = {"color" : "black", "linestyle" : "--", "linewidth" : 1.5})
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/f09f0415-18bd-4ff7-a126-eabf4bf41a64)
```
sns.boxplot(x = 'Pclass', y='Age', data=df, palette='rainbow')
plt.title("Age by Passenger Class, Titanic")
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/dc06c423-9c97-4e7b-aa6a-0cdeb983e3a8)

### Violin Plot
```
sns.violinplot(x = "day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette = 'Set1', inner = "quartile")

plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/97c8712f-8669-4809-818a-de839be57ef6)

```
import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x ='day', y ='tip', data = tip)
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/08bfcf1e-2456-48cc-844d-6a86ada308c4)
```
import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x = tip["total_bill"])
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/98dfda9d-149f-40d9-a732-3ffd43492bbf)
```
import seaborn as sns
sns.set(style = "whitegrid")
tips = sns.load_dataset("tips")
sns.violinplot(x = 'tip', y = 'day', data = tip)
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/cfbf6aee-a746-4515-adbd-812c6eb3ffb8)


### Density Plot
```
sns.kdeplot(data=df, shade=True)
plt.title('Density Plot of Passenger Ages')
plt.show()
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/3d47ad84-bf75-491e-8836-d1b7818f23c7)
```
import seaborn as sns
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

mart = pd.read_csv("supermarket.csv")
mart = mart[['Gender', 'Payment', 'Unit price', 'Quantity', 'Total', 'gross income']]
mart.head(10)
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/d9c6ae73-286b-4ee9-9ec3-94320bdfa9aa)

```
sns.kdeplot(data = mart, x = 'Total')
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/59649e38-5889-4448-a4c0-113c3986015d)

```
sns.kdeplot(data = mart, x = "Unit price")
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/280c059e-cfa0-471b-9702-e145fb0088da)

```
sns.kdeplot(data=mart)
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/1c277f9a-f572-4d16-a8fd-a0438758bf32)

```
sns.kdeplot(data=mart, x='Total', hue='Payment', multiple= 'stack')
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/6b1775c2-145d-4c31-b995-4154365fa586)

```
sns.kdeplot(data=mart, x='Total', hue='Payment', multiple='stack', linewidth=5, palette='Dark2', alpha=0.5)
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/36853e02-7de5-41f7-bd1c-653c3c0a8b5f)

```
sns.kdeplot(data=mart, x='Unit price', y='gross income')
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/7bcda72d-84f9-4b75-819a-61d8f1e1fe91)


## Heatmap
```
data = np.random.randint(low = 1, high = 100, size = (10, 10))
print("The data to be plotted.\n")
print(data)
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/fc3ebc47-94d6-4a24-90d3-d8f4dab98e94)

```
numeric_df = df.select_dtypes(include=['float64', 'int64'])
corr_matrix = numeric_df.corr()
sns.heatmap(corr_matrix, annot=True, cmap='coolwarm')
plt.title('Heatmap of Titanic Dataset')
plt.show()
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/323b2b56-1a7a-4fc1-a5aa-b8abb47ff632)

```
hm = sns.heatmap(data = data, annot=True)
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/4f812745-34a1-41c1-bb60-a04ebd27651c)

```
hm = sns.heatmap(data = data)
```
![image](https://github.com/Kousalya22008930/EXNO-6-DS/assets/119389108/6b8855b8-3aa5-4e87-8056-b5fec423443b)



# Result:
 
Thus, the Data Visualization using seaborn python library for the given data is implemented successfully
