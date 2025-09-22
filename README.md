### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 22.09.2025
### NAME: EZHIL NEVEDHA K
### REG.NO: 212223230055
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
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
```python
import pandas as pd
import matplotlib.pyplot as plt
df=pd.read_csv('clustervisitor.csv')
cluster={"Young":(df['Age']<=30),"Middle":((df['Age']>30) & (df['Age']<=50)),"Older":(df['Age']>50)}
print(cluster)
count=[]
for g,c in cluster.items():
  visitors=df[c]
  count.append(len(visitors))
  print(f'Visitors in {g} Group')
  print(visitors)
  print('Count of Groups')
  print(count)
plt.figure(figsize=(8, 6))
plt.bar(cluster.keys(), count, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()

```
### Output:
<img width="292" height="615" alt="image" src="https://github.com/user-attachments/assets/ba35a0eb-b03e-4c14-8eec-02f89e548ac5" />

<img width="305" height="492" alt="image" src="https://github.com/user-attachments/assets/45e83111-3f05-4d90-8781-a970272a91f7" />

<img width="575" height="405" alt="image" src="https://github.com/user-attachments/assets/c440454b-f216-4577-9e13-f27b453a209f" />


### Program 2:
```python
import pandas as pd
import matplotlib.pyplot as plt
df=pd.read_csv('clustervisitor (Salary).csv')
df1=df['Age']
df2=df['Salary']
df3=pd.concat([df1,df2],axis=1)
df3
from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans
sc=StandardScaler()
df4=sc.fit_transform(df3)
print(df4)
kmeans=KMeans(n_clusters=3,random_state=32)
df3['cluster']=kmeans.fit_predict(df3)
print(df3)
plt.scatter(df3['Age'],df3['Salary'],c=df3['cluster'])
plt.xlabel('Age')
plt.ylabel('Salary in thousands')
plt.title('Kmeans Cluster')
plt.show()
```
### Output:
<img width="249" height="507" alt="image" src="https://github.com/user-attachments/assets/9318c677-aec9-448e-ae08-9146e0f80d83" />

<img width="573" height="432" alt="image" src="https://github.com/user-attachments/assets/3bdd3110-1f83-4bf0-993a-e6734218fec2" />

### Result:
Thus, cluster and Visitor Segmentation for Navigation patterns have been implemented.
