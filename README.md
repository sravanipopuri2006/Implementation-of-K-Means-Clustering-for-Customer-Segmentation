# EX-08- Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program.
```

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: 
RegisterNumber:  
*/

import matplotlib.pyplot as plt
import pandas as pd
data=pd.read_csv('Mall_Customers.csv')
print(data)

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range(1,11):
    kmeans=KMeans(n_clusters=i,init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No.of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
print(y_pred)

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="brown",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="yellow",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="blue",label="cluster4")
plt.legend()
plt.title("consumer segments")


```

## Output:
## DATASET
![Screenshot 2024-05-04 232721](https://github.com/sravanipopuri2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139778301/1f21bfae-f901-4876-9938-5b25d3453d78)
## data.head()
![Screenshot 2024-05-04 232730](https://github.com/sravanipopuri2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139778301/07b7f7b0-0fe6-4d47-9324-f5e8a2b00a3e)
## data.info()
![Screenshot 2024-05-04 232740](https://github.com/sravanipopuri2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139778301/0760e944-2e37-40f6-ad60-6122409c676a)
## Checking if null values are present
![Screenshot 2024-05-04 232749](https://github.com/sravanipopuri2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139778301/7cebf8ff-cba9-4470-abc6-653c9f4d81c8)
## For loop to cluster data
![Screenshot 2024-05-04 232807](https://github.com/sravanipopuri2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139778301/79e6d32e-b817-4b48-ad71-50d4e3ddbc78)

## Elbow method graph
![Screenshot 2024-05-04 232826](https://github.com/sravanipopuri2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139778301/ba85aa5c-38cd-41e3-b922-6f6b49de9254)
## Fitting of data in cluster
![Screenshot 2024-05-04 232842](https://github.com/sravanipopuri2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139778301/c0396bce-2e4b-4f60-802a-399378487675)
## Predicting the values
![Screenshot 2024-05-04 232853](https://github.com/sravanipopuri2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139778301/1bdfb664-1f26-4358-83c1-8eb988f548d2)
## Kmeans clustering graph
![Screenshot 2024-05-04 232908](https://github.com/sravanipopuri2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139778301/16d1d56c-6fb7-4964-96e7-3becb1e45fb4)












## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
