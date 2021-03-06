---
title       : Car Road Test Trends
subtitle    : Analysis
author      : Pallav Mishra
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Agenda

1. Overview
2. Data Preparation and Analysis
3. Visualization
4. Conclusion

--- .class #id 

## Overview

Using the Motor Trend data (1974) that comes with R, I have built a simple UI.Using Shiny, I have shown the mean Miles per Gallon information, for cylinder and horsepower data entered through sliders. Reactive calculation is based on hitting the Submit button.

--- .class #id

## Data Preparation and Analysis

The datasource is the mtcars dataset that is built into the R default package. [Please refer to the server.R file where the data file has been loaded into Shiny]


```r
data <- mtcars
```


This simple example did not require any analysis apart from doing a mean of the Miles per Gallon information for the cylinder and horsepower information provided as an input through the UI form. The function to do this is provided in the "server.R" file.Here is the function doing the analysis


```r
tempfx <- function(x,y) {
  
  data <- mtcars
  
  temp <- data[data$cyl == x &
                data$hp <= y, ]
  out <- mean(temp$mpg)
  return (out)
}
```

--- .class #id

## Visualization



--- .class #id

## Conclusion

As is evident from the visual output, as the number of cylinders increase, for increasing horsepowers, there is a decrease in average Miles per gallon (mileage) of the car.








