### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 07.02.2026
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

### Program:
```python
cluster={"young":(df['Age']<=30),"Middle":((df['Age']>30)&(df['Age']<=50)),"Old":(df['Age']>50)}
count=[]
for group,condition in cluster.items():
  visitors=df[condition]
  count.append(len(visitors))
  print(f"The visitor on {group} age are")
  print(visitors)
  print("count=",len(visitors))
```
### Output:
<img width="687" height="775" alt="image" src="https://github.com/user-attachments/assets/6f6f93aa-7ee9-4c3d-a128-b6c62bdd3d17" />

### Visualization:
```python
import matplotlib.pyplot as plt
plt.figure(figsize=(8,6))
plt.bar(['Young','Middle','Old'],count,color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number if visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
### Output:
<img width="812" height="626" alt="image" src="https://github.com/user-attachments/assets/55e9195c-99d0-411a-8064-7bc9fc2c7ab6" />
### program 2
```
df1=df['Age']
df2=df['Income']
df3=pd.concat([df1,df2],axis=1)
s=StandardScaler()
newdf=s.fit_transform(df3);
k=KMeans(n_clusters=4,random_state=55)
df3['cluster']=k.fit_predict(newdf)
df3
```
output
<img width="282" height="611" alt="image" src="https://github.com/user-attachments/assets/ec7a4ec7-63f3-44b2-80bd-0ad97ad6f1cd" />

### Visualization
```
import matplotlib.pyplot as plt
plt.figure(figsize=(8,6))
plt.scatter(x=df3['Age'],y=df3['Income'],c=df3['cluster'])
plt.xlabel('Age')
plt.ylabel('Income')
plt.title('Visitor Distribution in Different Clusters')
plt.show()
```
output
<img width="487" height="342" alt="image" src="https://github.com/user-attachments/assets/138afac1-015a-434e-80e9-a4d7fa885a7a" />

### Result:
The Cluster and Visitor Segmentation for Navigation patterns is implemented  successfully.
