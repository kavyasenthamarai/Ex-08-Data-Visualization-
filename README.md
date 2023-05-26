# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE
NAME:K.KAVYA
REGISTER NUMBER:212222230065
```
# DATA:

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import seaborn as sbn
df=pd.read_csv("/content/Superstore.csv",encoding='windows-1252')
df.head()

# DATA CLEANING
df.info()

df.isnull().sum()

1.Which Segment has Highest sales?
sbn.barplot(x=df['Segment'],y=df['Sales'])
plt.title("Highest Sales of the segment")

2.Which City has Highest profit?
sbn.barplot(x=df['City'],y=df['Profit'])
plt.title("Highest Profit of cities")

City=df.loc[:,["City","Profit"]]
df.head(5)
City=City.groupby(by=["City"]).sum().sort_values(by="Profit")
plt.figure(figsize=(10,10))
sbn.barplot(x=City.index,y="Profit",data=City)
plt.xticks(rotation = 90)
plt.xlabel=("City")
plt.ylabel=("Profit")
plt.show()

3.Which ship mode is profitable?
sbn.barplot(x=df['Ship Mode'],y=df['Profit'])
plt.title("Profitable Ship Mode")

4.Sales of the product based on region.
sbn.barplot(x=df['Sales'], y=df['Region'])
plt.title("Sales of Product based on Region")

5.Find the relation between sales and profit.
sbn.lineplot(x=df['Sales'], y=df['Profit'])
plt.title("Relation between Sales and Profit")

6.Find the relation between sales and profit based on the following category. i) Segment ii)City iii)States iv)Segment and Ship Mode v)Segment, Ship mode and Region

## i) Segment
grouped_data = df.groupby('Segment')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('Segment')
ax.set_ylabel('Value')
ax.legend()
plt.show()

## ii) City
grouped_data = df.groupby('City')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('City')
ax.set_ylabel('Value')
ax.legend()
plt.show()

## iii) States
grouped_data = df.groupby('State')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('State')
ax.set_ylabel('Value')
ax.legend()
plt.show()

## iv)Segment and Ship Mode
grouped_data = df.groupby(['Segment', 'Ship Mode'])[['Sales', 'Profit']].mean()
pivot_data = grouped_data.reset_index().pivot(index='Segment', columns='Ship Mode', values=['Sales', 'Profit'])
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
pivot_data.plot(kind='bar', ax=ax)
ax.set_xlabel('Segment')
ax.set_ylabel('Value')
plt.legend(title='Ship Mode')
plt.show()

## v)Segment, Ship mode and Region
grouped_data = df.groupby(['Segment', 'Ship Mode','Region'])[['Sales', 'Profit']].mean()
pivot_data = grouped_data.reset_index().pivot(index=['Segment', 'Ship Mode'], columns='Region', values=['Sales', 'Profit'])
sns.set_style("whitegrid")
sns.set_palette("Set1")
pivot_data.plot(kind='bar', stacked=True, figsize=(10, 5))
plt.legend(title='Region')
plt.show()
```
# OUPUT
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/6bed549a-066e-4410-8758-39028a4943ad)
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/675655ea-b0fb-4c96-9ac5-62f429241640)
## data info:
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/64d611fb-a1a4-4f1f-872a-955c3280e426)
## DATA SET:
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/cd07f328-e9c8-446b-881b-1fb74a514068)
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/dc3853fd-b4bb-48d1-91f1-41bbc289e058)

![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/fc0b22f0-3f13-4038-8710-7ff45f52371e)
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/ee900acc-75d2-44c3-bfa5-c7feebc1180e)
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/2989ef16-4708-4451-90dc-855ccbf049bf)
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/558bc744-5637-4056-b47f-dbb22ceb40e3)
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/f34ae396-5788-4847-8a19-436efa7ac8a7)
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/7b2043a4-5cf9-43cc-96d6-c77527ceb7d4)
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/8fe91d06-e73c-4fc8-bc60-4a976964a4bd)
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/05187b93-b17b-4801-b7fd-5e7698189aef)
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/aa34018b-b120-4f91-a29d-2a06c6cbdf81)
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/20afe68a-2169-45cc-a640-1aa4373de1bb)
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/5d5821f8-8deb-41b5-843c-44c7ffecc3ea)

![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/685437bc-cf83-4da0-89cd-01c7c23cbc08)

![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/b177e805-083e-4261-9133-36ad9f8cc2a6)

![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/2741890b-43dc-4b23-a2db-4b0ba4f5b750)

![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/f0ddce69-a45b-4391-b33d-12098ea688be)
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/fbba8dc1-e579-4b43-ab10-0e7fbecd984e)
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/8dd2c2ab-d072-44c6-8965-0e874be27b54)
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/9ef36b1a-1f1a-4917-adf7-bfedf3c96b97)
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/3c6286cb-0bc2-4aea-a83a-16a7af762b2b)
![image](https://github.com/kavyasenthamarai/Ex-08-Data-Visualization-/assets/118668727/9b7c9a09-6056-4111-a338-c8f121190769)

# RESULT:
Hence the data visualization method for the given dataset applied successfully.
