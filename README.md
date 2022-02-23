# Lab2
---
title: "Homework4"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```


Link to git hub repository as follows: https://github.com/vbahirat/Lab2Vai.git


```{r}
choco <- read.csv("https://ds202-at-isu.github.io/labs/data/choco.csv")
head(choco)
```
```{r}
library(tidyverse)
str(choco)
```
```{r}
library(plyr)
count(choco, "Rating")
```
```{r}
is.null(choco$Rating)
```

No null values present. Thus total number of chocolate bars rated is 1852. 

```{r}
ggplot(choco,aes(x=Rating,fill=factor(Review.Date)))+geom_bar()
```


Lower ratings were in higher numbers for older years than recent years. Satisfactory ratings are seen in higher amounts after years 2014. This may indicate an increase in quality throughout the years as a maximum portion of the bar on for example rating 3 is towards the rrecent years and in 2 the maxmimum count is towards the older years. 

```{r}
ggplot(choco,aes(x=Rating))+geom_histogram()
```


The histogram above gives the frequency of ratings. The maximum ratings are obsevred for a rating of "3.5". Most of the data is observed towards the center. We can aslo see an outlier of a rating "1" and "5". These values disrupt the bell curve as weel. It clearly indicates in the several years the chocolate rating has never been too bad or too good.

```{r}
ggplot(choco,aes(x=Rating,fill=factor(Cocoa.Pct)))+geom_bar()
```


A fairly high amount of count is associated with Cocoa percentages above 67 percent for ratings from "2.5" to "4". This does indicate that high percent of cocoa are one of the factors that contribute to decentl and good ratings. 

```{r}
newchoco=dplyr::filter(choco,Company.Location%in% c("U.S.A.","France","Canada"))
```
```{r}
ggplot(newchoco,aes(x=Rating,fill=factor(Company.Location)))+geom_bar()
```


All the locations i.e. USA, Canda, France have different chocolate ratings starting from low to high. However, USA has a greater number of production and more covergae, thus a greater proportions above in the graph is covered by US. 

A new question for investigation includes the following:
Compare ratings across the Years for the filtered data set.
```{r}
ggplot(newchoco,aes(x=Rating,fill=factor(Review.Date)))+geom_bar()
```

Using the new data set. If we compare USA,Canada, France's Ratings across years we see as the years increases we see a higher proportion of good ratings than bad ratings. This graph has a high value for the average ratings that is from "3-3.75" and most values lean towards pink. This indicates in recent years more quantity of good rating bars were produced. However we also see some premium (rating=4) quality chocolates produced in a high quantity in year 2006.   

**Workflow- Working with Git individual assignment**
Working with Git is very easy. Specifically for this assignment I created a repository for Lab 2 in my Git. I created a new project in R and linked it to my repository on R. I answered the questions on the practice for homework. Pushed the code to the repository. If any one would wish to collaborate I would accept their pull request for easy collaboration. Git helps easy collaboration and helps it work together as teams easier. 
