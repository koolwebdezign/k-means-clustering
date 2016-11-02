# K-Means Clustering Demo
J Welch  
November 2, 2016  

# K-Means Clustering

This is a simple educational exercise that introduces the use of K-Means Clustering with R Studio.  I have chosen to follow the exercise as outlined per the following page at [WikiBooks.org](https://en.wikibooks.org/wiki/Data_Mining_Algorithms_In_R/Clustering/K-Means).  This page explains this important technique and then provides a simple Case Study that makes use of some country data complete with data related to the 'Per capita income', 'Literacy', 'Infant mortality', and 'Life expectancy'.

I copied the given data off the web page and created a CSV file entitled 'data.txt' as used within the Case Study.  I am going to follow the given code and create the result myself in R Studio.



```r
# import data (assume that all data in "data.txt" is stored as comma separated values)
x <- read.csv("data.txt", header=TRUE, row.names=1)

# show first 10 rows
head(x, n=10)
```

```
##                Per.capita.income Literacy Infant.mortality Life.expectancy
## Brazil                     10326     90.0            23.60            75.4
## Germany                    39650     99.0             4.08            79.4
## Mozambique                   830     38.7            95.90            42.1
## Australia                  43163     99.0             4.57            81.2
## China                       5300     90.9            23.00            73.0
## Argentina                  13308     97.2            13.40            75.3
## United Kingdom             34105     99.0             5.01            79.4
## South Africa               10600     82.4            44.80            49.3
## Zambia                      1000     68.0            92.70            42.4
## Namibia                     5249     85.0            42.30            52.9
```

```r
# run K-Means
km <- kmeans(x, 3, 15)

# print components of km
print(km)
```

```
## K-means clustering with 3 clusters of sizes 5, 7, 7
## 
## Cluster means:
##   Per.capita.income Literacy Infant.mortality Life.expectancy
## 1         13370.400    91.58        23.560000        68.96000
## 2          3267.286    70.50        56.251429        58.80000
## 3         35642.143    98.50         4.477143        80.42857
## 
## Clustering vector:
##         Brazil        Germany     Mozambique      Australia          China 
##              1              3              2              3              2 
##      Argentina United Kingdom   South Africa         Zambia        Namibia 
##              1              3              1              2              2 
##        Georgia       Pakistan          India         Turkey         Sweden 
##              2              2              2              1              3 
##      Lithuania         Greece          Italy          Japan 
##              1              3              3              3 
## 
## Within cluster sum of squares by cluster:
## [1]  57626083  20109876 158883600
##  (between_SS / total_SS =  94.1 %)
## 
## Available components:
## 
## [1] "cluster"      "centers"      "totss"        "withinss"    
## [5] "tot.withinss" "betweenss"    "size"         "iter"        
## [9] "ifault"
```

```r
# plot clusters
plot(x, col = km$cluster)

# plot centers
points(km$centers, col = 1:2, pch = 8)
```

![](k-means-demo_files/figure-html/unnamed-chunk-1-1.png)<!-- -->

