Task 1
================
Nicole Hawe
October 2, 2017

Before we begin I loaded the necessary packages:

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
library(knitr)
#to create a table with kable
library(dplyr)
library(stringr)
```

#### Find the Maximum and Minimum GDP per Capita for all Continents

Last Homework assignment we discovered that the gapminder component GdpPercap was a *number* and Continent was a *double*

Keeping that in mind, I found the min and max GdpPercap for each continent as follows:

``` r
n1 <- gapminder %>%
  group_by(continent) %>%
  summarize(max_gdp = max(gdpPercap), min_gdp = min(gdpPercap))
#first grouping by continent then summarizing
kable(n1)
```

| continent |   max\_gdp|    min\_gdp|
|:----------|----------:|-----------:|
| Africa    |   21951.21|    241.1659|
| Americas  |   42951.65|   1201.6372|
| Asia      |  113523.13|    331.0000|
| Europe    |   49357.19|    973.5332|
| Oceania   |   34435.37|  10039.5956|

I explored making the table a bit nicer using the knitr package and the kable function. I found this code [here](http://stat545.com/hw03_dplyr-and-more-ggplot2.html)

Next I wanted some visual representation of these stats so firstly I separated both the min and max gdpPercap for each continent in bar graphs:

``` r
ggplot(n1,aes(x=continent,y=max_gdp, fill=continent)) + 
  geom_bar(stat="identity", color="black")+
  ggtitle("Max GdpPerCap Per Continent")+
  theme(plot.title = element_text(hjust = 0.5))
```

![](Task_1_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-3-1.png)

``` r
ggplot(n1,aes(x=continent,y=max_gdp, fill=continent)) + 
  geom_bar(stat="identity", color="black")+
  ggtitle("Min GdpPerCap Per Continent")+
  theme(plot.title = element_text(hjust = 0.5))
```

![](Task_1_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-4-1.png)

Then I wanted to explore a graph with both the Min and Max GdpPerCap for each continent in a scatterplot:

``` r
b <- gapminder %>%
  group_by(continent) %>%
  filter(gdpPercap == max(gdpPercap) | gdpPercap == min(gdpPercap)) %>%
  ggplot(aes(x= continent, y= gdpPercap, colour= gdpPercap>15000)) +
  geom_point(show.legend=FALSE, size = 3)+
  ggtitle("Min and Max GdpPerCap Per Continent")+
  theme(plot.title=element_text(hjust=0.5))
b
```

![](Task_1_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-5-1.png)

Move on to [Task 2](https://github.com/nicolehawe/STAT545-HW-Hawe-Nicole/blob/master/HW03/Task_2.md)
