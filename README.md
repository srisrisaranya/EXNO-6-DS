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
x=[1,2,3,4,5]
y=[3,6,2,7,1]
sns.lineplot(x=x,y=y)
```
![image](https://github.com/user-attachments/assets/58a96d90-dccd-4655-be12-ee0a5a952f0a)

```
df=sns.load_dataset('tips')
df
```
![image](https://github.com/user-attachments/assets/9306b92e-8ae7-4cfa-b36e-3c20f8d8dce7)

```
sns.lineplot(x='total_bill',y='tip',data=df,hue='sex',linestyle='solid',legend='auto')
```
![image](https://github.com/user-attachments/assets/28ec14f0-4650-4b59-b007-d54653a9244d)

```
x=[1,2,3,4,5]
y1=[3,5,2,6,1]
y2=[1,6,4,3,8]
y3=[5,2,7,1,4]
sns.lineplot(x=x,y=y1)
sns.lineplot(x=x,y=y2)
sns.lineplot(x=x,y=y3)
plt.title('Multi-Line Plot')
plt.xlabel('X Label')
plt.ylabel('Y Lbel')
```
![image](https://github.com/user-attachments/assets/d2aafa38-51db-40ca-865d-f295daaf507d)

```
import seaborn as sns
import matplotlib.pyplot as plt
tips=sns.load_dataset('tips')
avg_total_bill=tips.groupby('day')['total_bill'].mean()
avg_tip=tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index,avg_total_bill,label='Total Bill')
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title("Average Total Bill and Tip by Day")
plt.legend()
```
![image](https://github.com/user-attachments/assets/ab5dbbd3-c672-4282-8168-76a99af1484a)

```
avg_total_bill=tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time')['tip'].mean()
p1=plt.bar(avg_total_bill.index,avg_total_bill,label='Total Bill',width=0.4)
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip',width=0.4)
plt.xlabel('Time of Day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Time of Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/66f8c214-cb01-4cf9-b3be-211d16229d3d)

```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![image](https://github.com/user-attachments/assets/ea26de06-4a78-4c91-aa2d-3ba80294000f)

```
import seaborn as sns
dt= sns.load_dataset('tips')
# Bar plot with hue parameter
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the week')
plt.ylabel('Total Bill')
plt.title('Total Bill by Day and Gender')
```
![image](https://github.com/user-attachments/assets/3baba960-3acd-4500-853c-8d41c467b602)

```
import pandas as pd 
tit = pd.read_csv("titanic_dataset.csv") 
tit
```
![image](https://github.com/user-attachments/assets/6939aca1-0639-49dc-8531-316c8c03a917)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```
![image](https://github.com/user-attachments/assets/3e2397c2-250a-4b3e-bc0c-c57b727effaa)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![image](https://github.com/user-attachments/assets/1bcd06a2-e16c-4cab-bac3-4fd9c753397a)

```
import seaborn as sns
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill',y='tip',hue='sex',data=tips)
plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![image](https://github.com/user-attachments/assets/3f4ad5c5-9491-4368-8d5f-a82e1835ffac)

```
import numpy as np
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```
![image](https://github.com/user-attachments/assets/87031174-bd8c-4ded-9cc9-98567b83844c)

```
sns.histplot(data = num_var, kde = True)
```
![image](https://github.com/user-attachments/assets/febcce9b-3478-4aaf-9017-998520c40b99)

```
df=pd.read_csv("titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```
![image](https://github.com/user-attachments/assets/c226c402-aa6b-4ecc-b9ab-cc7ce221be07)

```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
![image](https://github.com/user-attachments/assets/693e830a-c8c9-420a-9c74-52124ce7b81b)

```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color":"black","linestyle": "--", "linewidth": 1.5})
```
![image](https://github.com/user-attachments/assets/c848692d-f975-42b1-938c-0dc6845a4f3a)

```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6,
palette="Set3", inner="quartile")
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![image](https://github.com/user-attachments/assets/a366cb3a-089c-452c-8aea-2b304d34be22)

```
mart=pd.read_csv("titanic_dataset.csv")
mart
```
![image](https://github.com/user-attachments/assets/a6fa7629-003b-430f-8e6a-830afc7a3769)

```
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']]
mart.head(10)
```
![image](https://github.com/user-attachments/assets/57a52742-5520-4f17-a887-4a69eb489652)

```
sns.kdeplot(data=mart,x='PassengerId')
```
![image](https://github.com/user-attachments/assets/11aa8268-56df-427c-82a0-0fc8900a4454)

```
sns.kdeplot(data=mart,x='Age')
```
![image](https://github.com/user-attachments/assets/7404e62e-b617-4cb2-9dbf-b5d5df18b69d)

```
sns.kdeplot(data=mart)
```
![image](https://github.com/user-attachments/assets/3c6268d3-6091-4ed9-858c-6e714a764ab4)

```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```
![image](https://github.com/user-attachments/assets/4c6c4d37-c55e-4e28-96dc-c4d1b26fd5df)

```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```
![image](https://github.com/user-attachments/assets/ed2cd531-1866-4a6c-9425-9b1b260537c9)

```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```
![image](https://github.com/user-attachments/assets/a19d0905-2c74-446f-a362-4766aa670e60)

```
hm=sns.heatmap(data=data)
```
![image](https://github.com/user-attachments/assets/097ea9b4-b120-4da9-a287-db5aa2b6a832)


# Result:
Thus, all the data visualization techniques of seaborn has been implemented.
