
---
title: "Hw01_gapminder"
author: "Nicole Hawe"
date: "September 14, 2017"
output: github_document

## HW01 Assignment Addition 

- bullet 1
- bullet 2


```r
x <- rnorm(100)
y <- rnorm(100)
plot(x, y)
```

![](Hw01_gapminder_files/figure-html/unnamed-chunk-1-1.png)<!-- -->


```r
summary(x)
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
## -2.5955 -0.6194  0.1135  0.1160  0.7974  2.7822
```


## R Markdown

When you click the **Knit** button a document will be generated that includes both content as well as the output of any embedded R code chunks within the document. You can embed an R code chunk like this:


```r
summary(cars)
```

```
##      speed           dist       
##  Min.   : 4.0   Min.   :  2.00  
##  1st Qu.:12.0   1st Qu.: 26.00  
##  Median :15.0   Median : 36.00  
##  Mean   :15.4   Mean   : 42.98  
##  3rd Qu.:19.0   3rd Qu.: 56.00  
##  Max.   :25.0   Max.   :120.00
```

## Including Plots

You can also embed plots, for example:

![](Hw01_gapminder_files/figure-html/pressure-1.png)<!-- -->

Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.
