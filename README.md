# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages.
2. Read the given csv file and display the few contents of the data.
3. Import KMeans and use for loop to calculate the within cluster sum of squares the data.
4. Plot the wcss for each iteration, also known as the elbow method plot.
5. Predict the clusters and plot them.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: K.Balaji
RegisterNumber: 212221230011
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv('Mall_Customers (1).csv')
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
### 1. data.head() function
![image](https://github.com/balaji-21005757/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94372294/75422c47-3f52-44dc-bcb7-005fb0d9a0f1)
### 2. data.info()
![image](https://github.com/balaji-21005757/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94372294/cf292fa5-09ea-4bc3-9cb9-e1efa65ce231)
### 3. data.isnull().sum() function
![image](https://github.com/balaji-21005757/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94372294/fadad85d-fbb2-4750-a6c9-ff751c022386)
### 4. Elbow method Graph
![image](https://github.com/balaji-21005757/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94372294/fbccec1e-186d-4ca6-a5b0-75a17500b721)
### 5. KMeans clusters
![image](https://github.com/balaji-21005757/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94372294/139cb40d-928d-4590-a9e8-95e0658ba167)
### 6. Customer segments Graph
![image](https://github.com/balaji-21005757/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94372294/b3400923-dc3c-4b0a-a67c-ff40b095e5f3)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
