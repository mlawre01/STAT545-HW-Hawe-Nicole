Exploration into Gapminder
================
Nicole Hawe
September 25, 2017

Introduction
------------

Within this second homework assignment, we explore the Gapminder dataset in more detail.

This page will cover the work flow for:

-   Overall Properties of the Gapminder Dataset

-   Variable Property Exploration

-   Data Visualization using ggplot2

-   Data Filtering/ Piping

-   Reflections

Overall Properties of the Dataset
---------------------------------

The first step is to load the Gapminder dataset and packages we need!

``` r
library(gapminder)
library(tidyverse)
```

    ## Loading tidyverse: ggplot2
    ## Loading tidyverse: tibble
    ## Loading tidyverse: tidyr
    ## Loading tidyverse: readr
    ## Loading tidyverse: purrr
    ## Loading tidyverse: dplyr

    ## Conflicts with tidy packages ----------------------------------------------

    ## filter(): dplyr, stats
    ## lag():    dplyr, stats

``` r
library(ggplot2)
```

So the assignment begins with the question: what is Gapminder? Is it a data.frame, a matrix, a vector, a list? Well, I decided to check this by using typeof() function.

``` r
typeof(gapminder)
```

    ## [1] "list"

However I would like to know the class of gapminder

``` r
class(gapminder)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

It appears to be a data frame, or more specifically a tibble!

Next, information regarding the struture of the dataset was asked such as:

-   How many variables/columns do we have? We can use ncol in R

-   How many rows/observations do we have? We can use nrow in R

``` r
ncol(gapminder)
```

    ## [1] 6

``` r
nrow(gapminder)
```

    ## [1] 1704

So it looks like this dataset has 6 columns with 1704 rows!

The it was asked whether we can get these facts about “extent” or “size” in more than one way? Can you imagine different functions being useful in different contexts?

we can find the length by

``` r
length(gapminder)
```

    ## [1] 6

Or the dimensions by

``` r
dim(gapminder)
```

    ## [1] 1704    6

We can also find the names of all th columns by

``` r
names(gapminder)
```

    ## [1] "country"   "continent" "year"      "lifeExp"   "pop"       "gdpPercap"

Or get an overall sense of the structure using

``` r
str(gapminder)
```

    ## Classes 'tbl_df', 'tbl' and 'data.frame':    1704 obs. of  6 variables:
    ##  $ country  : Factor w/ 142 levels "Afghanistan",..: 1 1 1 1 1 1 1 1 1 1 ...
    ##  $ continent: Factor w/ 5 levels "Africa","Americas",..: 3 3 3 3 3 3 3 3 3 3 ...
    ##  $ year     : int  1952 1957 1962 1967 1972 1977 1982 1987 1992 1997 ...
    ##  $ lifeExp  : num  28.8 30.3 32 34 36.1 ...
    ##  $ pop      : int  8425333 9240934 10267083 11537966 13079460 14880372 12881816 13867957 16317921 22227415 ...
    ##  $ gdpPercap: num  779 821 853 836 740 ...

This information can be found in several way!

Next we needed to find the type of each variable in this dataset using the typeof function

``` r
typeof(gapminder$country)
```

    ## [1] "integer"

``` r
typeof(gapminder$continent)
```

    ## [1] "integer"

``` r
typeof(gapminder$year)
```

    ## [1] "integer"

``` r
typeof(gapminder$lifeExp)
```

    ## [1] "double"

``` r
typeof(gapminder$pop)
```

    ## [1] "integer"

``` r
typeof(gapminder$gdpPercap)
```

    ## [1] "double"

Exploration of Individual Variables
-----------------------------------

For this part of the homework assignment we were to pick at least one categorical variable and at least one quantitative variable to explore.

For my categorical variable I chose **Year**

For my quantitative variable I chose **LifeExp**

For these we needed to find the possible values (or range, whichever is appropriate) of each variable?

What values are typical? What’s the spread? What’s the distribution?

So beginning with Year:

I wanted a nice summary to start with

``` r
summary(gapminder$year)
```

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##    1952    1966    1980    1980    1993    2007

``` r
table(gapminder$year)
```

    ## 
    ## 1952 1957 1962 1967 1972 1977 1982 1987 1992 1997 2002 2007 
    ##  142  142  142  142  142  142  142  142  142  142  142  142

From this quick summary and table I see that the minimum year is 1952 and it ranges to the maximum being 2007. Both the median and mean are 1980. I also appears that samples were taken every 5 years starting in 1952.

Moving onto the quantitative variable LifeExp:

``` r
summary(gapminder$lifeExp)
```

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   23.60   48.20   60.71   59.47   70.85   82.60

From this summary we can see the minimum value is 23.60 whereas the max is 82.60. This is quite a large spread. The median lies at 60.71 and the mean at 59.47.

For a value such as LifeExp a table may be too large and unuseful.

A quick plot can sometimes help though!

``` r
hist(gapminder$lifeExp)
```

![](Exploration_into_Gapminder_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-15-1.png)
