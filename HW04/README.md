
# Homework Assignment #4 

***

Welcome!

This assignment contains two parts that are meant to to solidify our data wrangling skills by working on some realistic problems in the grey area between data aggregation and data reshaping.

Find the Markdown file for the assignment [here]()

Go Back to the main page of my repo [here]()

All my resources are scattered throughout my assignment!


### Part 1: Reshape

**Problem:** You have data in one “shape” but you wish it were in another. Usually this is because the alternative shape is superior for presenting a table, making a figure, or doing aggregation and statistical analysis.

**Solution:** Reshape your data. For simple reshaping, _gather()_ and _spread()_ from tidyr will suffice. Do the thing that it possible / easier now that your data has a new shape.

*Activity #3: Compute some measure of life expectancy (mean? median? min? max?) for all possible combinations of continent and year. Reshape that to have one row per year and one variable for each continent. Or the other way around: one row per continent and one variable per year.
- Use knitr::kable() to make these tables look pretty in your rendered homework.
- Is there a plot that is easier to make with the data in this shape versis the usual form? If so (or you think so), try it! Reflect.*



### Part 2: Join 

**Problem:** You have two data sources and you need info from both in one new data object.

**Solution:** Perform a join, which borrows terminology from the database world, specifically SQL.

* Activity #1: Create a second data frame, complementary to Gapminder. Join this with (part of) Gapminder using a  dplyr join function and make some observations about the process and result. Explore the different types of joins. Examples of a second data frame you could build:
One row per country, a country variable and one or more variables with extra info, such as language spoken, NATO membership, national animal, or capitol city. One row per continent, a continent variable and one or more variables with extra info, such as northern versus southern hemisphere.*

**PLUS Bonus:** Explore the base function merge(), which also does joins. Compare and contrast with dplyr joins.

***

#### I then conclude the assignment with some reflections

I look forward to hearing your feedback!
