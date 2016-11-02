# K-Means Clustering

This is a simple educational exercise that introduces the use of K-Means Clustering with R Studio.  I have chosen to follow the exercise as outlined per the following page at [WikiBooks.org](https://en.wikibooks.org/wiki/Data_Mining_Algorithms_In_R/Clustering/K-Means).  This page explains this important technique and then provides a simple Case Study that makes use of some country data complete with data related to the 'Per capita income', 'Literacy', 'Infant mortality', and 'Life expectancy'.

I copied the given data off the web page and created a CSV file entitled 'data.txt' as used within the Case Study.  I am going to follow the given code and create the result myself in R Studio.

```
# import data (assume that all data in "data.txt" is stored as comma separated values)
x <- read.csv("data.txt", header=TRUE, row.names=1)

# run K-Means
km <- kmeans(x, 3, 15)
 
# print components of km
print(km)

# plot clusters
plot(x, col = km$cluster)
# plot centers
points(km$centers, col = 1:2, pch = 8)
```