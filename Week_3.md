---
title: "Week 3"
author: "Miranda Gilbert"
date: "7/16/2019"
output: 
  html_document: 
    keep_md: yes
---



## R Markdown

This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.

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

![](Week_3_files/figure-html/pressure-1.png)<!-- -->

Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.

**4.4 Practice**
  1. The code doesnt work because the I in variable was typed with a character that is missing the top dot, so it isnt the same code anymore. 
  2. The first two commands ran correctly, so I am unsure how they are incorrect. However the last code has filter incorrectly spelled, and that's why it didn't work.
  3. Alt shift K pulls up the quick command keyboard for my computer. I can get to the same place by looking up keybaord shortcuts using help. 
**5.2.4 Exercises**
  1.1   filter(flights, arr_delay >= 120)
  # A tibble: 10,200 x 19
    year month   day dep_time sched_dep_time dep_delay
   <int> <int> <int>    <int>          <int>     <dbl>
 1  2013     1     1      811            630       101
 2  2013     1     1      848           1835       853
 3  2013     1     1      957            733       144
 4  2013     1     1     1114            900       134
 5  2013     1     1     1505           1310       115
 6  2013     1     1     1525           1340       105
 7  2013     1     1     1549           1445        64
 8  2013     1     1     1558           1359       119
 9  2013     1     1     1732           1630        62
10  2013     1     1     1803           1620       103
  
  1.4  filter(flights, month %in% c(7,8,9))
  A tibble: 86,326 x 19
    year month   day dep_time sched_dep_time dep_delay
   <int> <int> <int>    <int>          <int>     <dbl>
 1  2013     7     1        1           2029       212
 2  2013     7     1        2           2359         3
 3  2013     7     1       29           2245       104
 4  2013     7     1       43           2130       193
 5  2013     7     1       44           2150       174
 6  2013     7     1       46           2051       235
 7  2013     7     1       48           2001       287
 8  2013     7     1       58           2155       183
 9  2013     7     1      100           2146       194
10  2013     7     1      100           2245       135
  1.5  filter(flights, dep_delay <= 0, arr_delay >= 120)
  A tibble: 29 x 19
    year month   day dep_time sched_dep_time dep_delay
   <int> <int> <int>    <int>          <int>     <dbl>
 1  2013     1    27     1419           1420        -1
 2  2013    10     7     1350           1350         0
 3  2013    10     7     1357           1359        -2
 4  2013    10    16      657            700        -3
 5  2013    11     1      658            700        -2
 6  2013     3    18     1844           1847        -3
 7  2013     4    17     1635           1640        -5
 8  2013     4    18      558            600        -2
 9  2013     4    18      655            700        -5
10  2013     5    22     1827           1830        -3
  1.7  filter(flights, dep_time >= 0, dep_time <= 600)
  A tibble: 9,344 x 19
    year month   day dep_time sched_dep_time dep_delay
   <int> <int> <int>    <int>          <int>     <dbl>
 1  2013     1     1      517            515         2
 2  2013     1     1      533            529         4
 3  2013     1     1      542            540         2
 4  2013     1     1      544            545        -1
 5  2013     1     1      554            600        -6
 6  2013     1     1      554            558        -4
 7  2013     1     1      555            600        -5
 8  2013     1     1      557            600        -3
 9  2013     1     1      557            600        -3
10  2013     1     1      558            600        -2
  2. between() is a shortcut for x >= left & x <= right. number 1.7 could also be written as: filter(flights, between(dep_time, 0 , 600))
  3. 8255 flights are missign departure time. sum(is.na(flights$dep_time)). There is also no departure delay because there was no departure. 
**5.3.1 Exercises**
  1. head(arrange(flights, desc(is.na(dep_delay))))
  A tibble: 6 x 19
   year month   day dep_time sched_dep_time dep_delay
  <int> <int> <int>    <int>          <int>     <dbl>
1  2013     1     1       NA           1630        NA
2  2013     1     1       NA           1935        NA
3  2013     1     1       NA           1500        NA
4  2013     1     1       NA            600        NA
5  2013     1     2       NA           1540        NA
6  2013     1     2       NA           1620        NA
  2. head(arrange(flights, desc(dep_delay)))
   A tibble: 6 x 19
   year month   day dep_time sched_dep_time dep_delay
  <int> <int> <int>    <int>          <int>     <dbl>
1  2013     1     9      641            900      1301
2  2013     6    15     1432           1935      1137
3  2013     1    10     1121           1635      1126
4  2013     9    20     1139           1845      1014
5  2013     7    22      845           1600      1005
6  2013     4    10     1100           1900       960
head(arrange(flights, dep_delay))
A tibble: 6 x 19
   year month   day dep_time sched_dep_time dep_delay
  <int> <int> <int>    <int>          <int>     <dbl>
1  2013    12     7     2040           2123       -43
2  2013     2     3     2022           2055       -33
3  2013    11    10     1408           1440       -32
4  2013     1    11     1900           1930       -30
5  2013     1    29     1703           1730       -27
6  2013     8     9      729            755       -26
  3. head(arrange(flights, air_time))
  A tibble: 6 x 19
   year month   day dep_time sched_dep_time dep_delay
  <int> <int> <int>    <int>          <int>     <dbl>
1  2013     1    16     1355           1315        40
2  2013     4    13      537            527        10
3  2013    12     6      922            851        31
4  2013     2     3     2153           2129        24
5  2013     2     5     1303           1315       -12
6  2013     2    12     2123           2130        -7
  4. head(arrange(flights, desc(distance)))
  A tibble: 6 x 19
   year month   day dep_time sched_dep_time dep_delay
  <int> <int> <int>    <int>          <int>     <dbl>
1  2013     1     1      857            900        -3
2  2013     1     2      909            900         9
3  2013     1     3      914            900        14
4  2013     1     4      900            900         0
5  2013     1     5      858            900        -2
6  2013     1     6     1019            900        79
  head(arrange(flights, distance))
  A tibble: 6 x 19
   year month   day dep_time sched_dep_time dep_delay
  <int> <int> <int>    <int>          <int>     <dbl>
1  2013     7    27       NA            106        NA
2  2013     1     3     2127           2129        -2
3  2013     1     4     1240           1200        40
4  2013     1     4     1829           1615       134
5  2013     1     4     2128           2129        -1
6  2013     1     5     1155           1200        -5
**5.4.1 Exercises**
  1. select(flights, dep_time, dep_delay, arr_time, arr_delay)
  select(flights, starts_with('dep'), starts_with('arr'))
  2. Repeated variables are not repeated in the final chart.
  3. one_of() matches varaible names in a character vector. It can be used to create a select list without using select. 
  4. It seems like the function is not case sensitive by default which is why capital TIME gets the same results as lower case time. Making ignore.case() false makes the function case sensitive. 
**5.5.2 Exercises**
  1. flights <- mutate(flights,
+                   dep_time_mins = dep_time %/% 100 * 60 + dep_time %% 100,
+                   sched_dep_time_mins = sched_dep_time %/% 100 * 60 +
+                       sched_dep_time %% 100)
  2. flights %>% mutate(flight_time = arr_time - dep_time) %>%
+     select(air_time, flight_time)
# A tibble: 336,776 x 2
   air_time flight_time
      <dbl>       <int>
 1      227         313
 2      227         317
 3      160         381
 4      183         460
 5      116         258
 6      150         186
 7      158         358
 8       53         152
 9      140         281
10      138         195
  I expected that airtime and flight time would be the same, however that was not the case. To fix it, I am going to switch the time to minutes to see if that fixes the timing. 
  flights <- mutate(flights,
+                   arr_time_mins = arr_time %/% 100 * 60 + arr_time %% 100)
> 
> flights <- mutate(flights, flight_time = arr_time_mins - dep_time_mins)
> 
> select(flights, air_time, flight_time)
# A tibble: 336,776 x 2
   air_time flight_time
      <dbl>       <dbl>
 1      227         193
 2      227         197
 3      160         221
 4      183         260
 5      116         138
 6      150         106
 7      158         198
 8       53          72
 9      140         161
10      138         115

  They are still not the same...
  3. Schedule departure time plus departure delay equals departure time. 
  A tibble: 336,776 x 3
   dep_time sched_dep_time dep_delay
      <int>          <int>     <dbl>
 1      517            515         2
 2      533            529         4
 3      542            540         2
 4      544            545        -1
 5      554            600        -6
 6      554            558        -4
 7      555            600        -5
 8      557            600        -3
 9      557            600        -3
10      558            600        -2

  4. head(arrange(flights, min_rank(desc(dep_delay))), 10)
  A tibble: 10 x 23
    year month   day dep_time sched_dep_time dep_delay
   <int> <int> <int>    <int>          <int>     <dbl>
 1  2013     1     9      641            900      1301
 2  2013     6    15     1432           1935      1137
 3  2013     1    10     1121           1635      1126
 4  2013     9    20     1139           1845      1014
 5  2013     7    22      845           1600      1005
 6  2013     4    10     1100           1900       960
 7  2013     3    17     2321            810       911
 8  2013     6    27      959           1900       899
 9  2013     7    22     2257            759       898
10  2013    12     5      756           1700       896
  5. [1]  2  4  6  5  7  9  8 10 12 11
Warning message:
In 1:3 + 1:10 :
  longer object length is not a multiple of shorter object length
  THe shorter vector is repeated to match the longer vector.
  
**5.6.7 Exercises**
  5. LGA has highest departure delay for F9. 
   
