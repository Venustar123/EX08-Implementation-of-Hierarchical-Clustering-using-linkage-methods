# EX8-Implementation of Hierarchical Clustering using linkage methods
## DATE:
## AIM:
To implement Hierarchical Clustering using single and complete linkage method

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.compute the distance between every pair of data points,resulting in a distance matrix

2.assign each data point to its own individual cluster

3.using a linkage criterion,find the two closest cluster and merge them

4.visualize the hierarchical clustering as a dendrogram

## Program:
```
Program to implement Hierarchical Clustering using single and complete linkage method
Developed by:BASHA VENU
RegisterNumber:2305001005

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy.cluster.hierarchy import dendrogram, linkage,fcluster
from sklearn.preprocessing import StandardScaler
df = pd.read_csv("/content/Hclus_EX8.csv")
df.head()
x = df[['StudentID','Marks']].values
x
z=linkage(x,method='complete')
plt.figure(figsize=(5,2))
plt.title("Dendogram for student segmentation")
labels=range(1,len(df)+1)
dendrogram(z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
max_cluster=2
clusters=fcluster(z,max_cluster,criterion='maxclust')
clusters
plt.figure(figsize=(5,2))
plt.scatter(x[:,0],x[:,1],c=clusters,cmap='rainbow',s=100)
plt.title("Student segmented(Hierarchical clustering)")
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
z=linkage(x,method='single')
plt.figure(figsize=(5,2))
plt.title("Dendogram for student segmentation")
labels=range(1,len(df)+1)
dendrogram(z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
```

## Output:

![image](https://github.com/user-attachments/assets/4075978c-fa80-45e1-9903-1da2ab7193d0)

![image](https://github.com/user-attachments/assets/140a7305-a0d4-4f9b-9937-b090cbb6552e)

![image](https://github.com/user-attachments/assets/19829ee3-58c8-4205-a1db-1cc72ad7ae18)

![image](https://github.com/user-attachments/assets/90fbcd66-835a-4ba2-8b5c-bab3edb05e3a)

![image](https://github.com/user-attachments/assets/f1e835d1-cc1e-4dbb-991d-ffed915bb705)


## Result:
Thus the implementation of Hierarchical Clustering using single and complete linkage method in python programming and verified successfully.
