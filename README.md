### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
##### DATE: 19-09-2025
##### REGISTER NUMBER : 212223040252
##### NAME : ZAFREEN J

### AIM:
To implement Cluster and Visitor Segmentation for Navigation patterns in Python.

### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program 1:
```


import pandas as pd

df=pd.read_csv(r"C:\Users\admin\Downloads\clustervisitor.csv")
df

cluster={"Young":(df['Age']<=30),"Middle":(df['Age']>30 & (df['Age']<=50)),"Old":(df['Age']>50)}
print(cluster)

count=[]
for g,c in cluster.items():
    visitors=df[c]
    count.append(len(visitors))
    print(f"Visistors in {g} Group")
    print(visitors)
    print(count)

import matplotlib.pyplot as plt
plt.figure(figsize=(8, 6))
plt.bar(cluster.keys(), count, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()

```
### Output:


<img width="976" height="729" alt="image" src="https://github.com/user-attachments/assets/8062c93a-6021-489d-8408-2f809db69b13" />

<img width="776" height="764" alt="image" src="https://github.com/user-attachments/assets/7e7ee41c-ba4a-4f53-865d-538b6b1633dc" />

<img width="752" height="732" alt="image" src="https://github.com/user-attachments/assets/e304aad2-4758-4ad8-a86b-42c7084f9cca" />

### Program2:

```

import pandas as pd
df=pd.read_csv(r"C:\Users\admin\Downloads\clustervisitor (Salary).csv")
df

df1 = df['Age']
df2 = df['Salary']
df3 = pd.concat([df1, df2],axis=1)   
df3

from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans

sc=StandardScaler()
scaleddata=sc.fit_transform(df3)
print(scaleddata)

kmeans=KMeans(n_clusters=3,random_state=42)
df3['cluster']=kmeans.fit_predict(df3)
df3

plt.scatter(df3['Age'],df3['Salary'],c=df3['cluster'])
plt.xlabel("Age")
plt.ylabel("Salary in Thousands")
plt.show()

```
### Output:


<img width="720" height="664" alt="image" src="https://github.com/user-attachments/assets/bbaae282-880b-410b-8ac3-2f04a781878d" />


<img width="862" height="766" alt="image" src="https://github.com/user-attachments/assets/a01d31fc-175d-4997-b36f-b6d4a731c484" />



<img width="914" height="552" alt="image" src="https://github.com/user-attachments/assets/0c0b50dc-cc54-4ab5-bcc3-ec9a1a1e70c1" />


### Result:
Cluster and Visitor Segmentation for Navigation patterns in Python is implemented successfully.
