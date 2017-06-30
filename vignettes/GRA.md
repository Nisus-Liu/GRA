

# Grey Relational Analysis(GRA)

Grey Relational Analysis include two important function.
First function: grey relational degree, which is similar to orrelation coefficient, if you want to evaluate some units, please transpose data frame before using this function. Second funtion: grey clustering, like hierarchical clustering, see `hclust`.

## Grey Relational Degree

There are two usage of grey relational degree. This algorithm is to measure similarity of two variables, just like `cor`. You can transpose your data set if you want to evaluate some units.

* One is to inspect correlation of two variables, data type like:

| reference | v1 | v2 | v3 |
|-----------|----|----|----|
|    1.2    | 1.8|0.9 | 8.4|
|    0.11   | 0.3|0.5 | 0.2|
|    1.3    | 0.7|0.12|0.98|
|    1.9    |1.09|2.8 |0.99|

`reference`: reference variable, grey relational degree between `reference` and `v1`... approximately measures the similarity of `reference` and `v1`.


* Another is to evaluate good or bad about some units.

| units | v1 | v2 | v3 |
|-----------|----|----|----|
|    jiangsu   | 1.8|0.9 | 8.4|
|    zhejiang   | 0.3|0.5 | 0.2|
|    anhui    | 0.7|0.12|0.98|
|    fujian    |1.09|2.8 |0.99|


### Example



```r
## generate data
refer = c(1,1,1,1)
liaoning = c(0.064, 0.082,0.978,0.423)
shandong = c(0.101,0.3,1,0.917)
jiangsu = c(0.114,0.14,0.943, 0.315)
zhejiang = c(0.102,0.147,0.934,0.395)
fujian = c(0.022,0.053,0.927,0.061)
guangdong = c(1,1,0.012,1)
economyCompare = data.frame(refer, liaoning, shandong, jiangsu, zhejiang, fujian, guangdong)
rownames(economyCompare) = c("indGV", "indVA", "profit", "incomeTax")

## Grey Relational Degree
greyRelDegree = GRA(economyCompare)
greyRelDegree


```



## Grey Clustering


### Example

```r
## Grey Clustering
GRA(economyCompare, cluster = T)
```


