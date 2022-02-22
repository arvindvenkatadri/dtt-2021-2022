---
title: "My Work on R"
author: "Niharika Vinuthan"
date: "20/02/2022"
slug: []
categories: []
tags: []
image: https://www.alice-in-wonderland.net/wp-content/uploads/1book5.jpg
caption: ''
preview: yes
output:
  blogdown::html_page:
    toc: no
    fig_width: 5
    fig_height: 5
    keep_md: yes
description: Hi there! I'm Niharika and I recently started working with R and using it as a medium for creating different work.
---



## Introduction

Hi there! I'm Niharika and I recently started working with R and using it as a medium for creating different work. I've never been a fan of coding and when I first started this course, I was uncertain about how it'd work for me but I decided to keep an open mind and work with it. But it turns out, that coding isn't actually that bad and this course has actually been one of my favorites so far. I'm glad I got to work with Arvind and everyone in class on this and it's definitely something I'm going to use in the future!  

Here you'll find some graphs/networks that I've worked on during the entire course of learning R. I'm including my favorite ones so far!

## Graph 1 - Plotting penguins: Islands vs Sex

The first dataset I chose is that of penguins. The columns include species, island, bill length, bill depth, flipper length, body mass, sex and year. the names of these columns are with reference to the penguins and answer questions like which island has the most male penguins? Or which species of penguins has the largest flipper length? 


```r
names(penguins) # Column, i.e. Variable names
```

```
## [1] "species"           "island"            "bill_length_mm"   
## [4] "bill_depth_mm"     "flipper_length_mm" "body_mass_g"      
## [7] "sex"               "year"
```

```r
head(penguins) # first six rows
```

```
## # A tibble: 6 x 8
##   species island bill_length_mm bill_depth_mm flipper_length_~ body_mass_g sex  
##   <fct>   <fct>           <dbl>         <dbl>            <int>       <int> <fct>
## 1 Adelie  Torge~           39.1          18.7              181        3750 male 
## 2 Adelie  Torge~           39.5          17.4              186        3800 fema~
## 3 Adelie  Torge~           40.3          18                195        3250 fema~
## 4 Adelie  Torge~           NA            NA                 NA          NA <NA> 
## 5 Adelie  Torge~           36.7          19.3              193        3450 fema~
## 6 Adelie  Torge~           39.3          20.6              190        3650 male 
## # ... with 1 more variable: year <int>
```

```r
tail(penguins) # Last six rows
```

```
## # A tibble: 6 x 8
##   species island bill_length_mm bill_depth_mm flipper_length_~ body_mass_g sex  
##   <fct>   <fct>           <dbl>         <dbl>            <int>       <int> <fct>
## 1 Chinst~ Dream            45.7          17                195        3650 fema~
## 2 Chinst~ Dream            55.8          19.8              207        4000 male 
## 3 Chinst~ Dream            43.5          18.1              202        3400 fema~
## 4 Chinst~ Dream            49.6          18.2              193        3775 male 
## 5 Chinst~ Dream            50.8          19                210        4100 male 
## 6 Chinst~ Dream            50.2          18.7              198        3775 fema~
## # ... with 1 more variable: year <int>
```

```r
dim(penguins) # Size of dataset
```

```
## [1] 344   8
```

```r
# Check for missing data
any(is.na(penguins) == TRUE)
```

```
## [1] TRUE
```

```r
glimpse(penguins)
```

```
## Rows: 344
## Columns: 8
## $ species           <fct> Adelie, Adelie, Adelie, Adelie, Adelie, Adelie, Adel~
## $ island            <fct> Torgersen, Torgersen, Torgersen, Torgersen, Torgerse~
## $ bill_length_mm    <dbl> 39.1, 39.5, 40.3, NA, 36.7, 39.3, 38.9, 39.2, 34.1, ~
## $ bill_depth_mm     <dbl> 18.7, 17.4, 18.0, NA, 19.3, 20.6, 17.8, 19.6, 18.1, ~
## $ flipper_length_mm <int> 181, 186, 195, NA, 193, 190, 181, 195, 193, 190, 186~
## $ body_mass_g       <int> 3750, 3800, 3250, NA, 3450, 3650, 3625, 4675, 3475, ~
## $ sex               <fct> male, female, female, NA, female, male, female, male~
## $ year              <int> 2007, 2007, 2007, 2007, 2007, 2007, 2007, 2007, 2007~
```

I'm going to be plotting a geom_density graph which compares the sex and island variables of the dataset. This graph answers the metaquestion: Which sex of penguins is prominent on each island?


```r
ggplot(penguins) + geom_density(aes(x = sex, 
                                fill = island),
                            position = "stack")
```

```
## Warning: Groups with fewer than two data points have been dropped.
```

```
## Warning: Removed 1 rows containing missing values (position_stack).
```

<img src="index_files/figure-html/plot-1-1.png" width="480" />
**Conclusion -The graph shows that overall the female penguins populate the islands more than the male penguins.**

## Graph 2 - Graph on Fictional characters: How much do the ratings vary with avg for each character?

The second dataset that I chose was the dataset on personalities of Fictional Characters. The columns include character_code, fictional_work, character_name, gender, spectrum, spectrum_low, spectrum_high, avg, ratings and sd (dropped column is is_emoji). Each of these columns directly correlate to the different characteristics of the fictional characters and helps us in comparing interesting factors such as spectrum, sd or character code.


```r
Fic_char <- read_delim("personalities.tsv",
    delim = "\t", escape_double = FALSE, 
    trim_ws = TRUE)
```

```
## Rows: 213600 Columns: 11
## -- Column specification --------------------------------------------------------
## Delimiter: "\t"
## chr (7): character_code, fictional_work, character_name, gender, spectrum, s...
## dbl (3): mean, ratings, sd
## lgl (1): is_emoji
## 
## i Use `spec()` to retrieve the full column specification for this data.
## i Specify the column types or set `show_col_types = FALSE` to quiet this message.
```

```r
Fic_char <- Fic_char %>% dplyr::rename("avg" = mean)
```

```r
data(Fic_char)
```

```
## Warning in data(Fic_char): data set 'Fic_char' not found
```

```r
names(Fic_char)
```

```
##  [1] "character_code" "fictional_work" "character_name" "gender"        
##  [5] "spectrum"       "spectrum_low"   "spectrum_high"  "is_emoji"      
##  [9] "avg"            "ratings"        "sd"
```

```r
glimpse(Fic_char)
```

```
## Rows: 213,600
## Columns: 11
## $ character_code <chr> "A/4", "A/4", "A/4", "A/4", "A/4", "A/4", "A/4", "A/4",~
## $ fictional_work <chr> "Alien", "Alien", "Alien", "Alien", "Alien", "Alien", "~
## $ character_name <chr> "Ash", "Ash", "Ash", "Ash", "Ash", "Ash", "Ash", "Ash",~
## $ gender         <chr> "male", "male", "male", "male", "male", "male", "male",~
## $ spectrum       <chr> "BAP1", "BAP2", "BAP3", "BAP4", "BAP5", "BAP6", "BAP7",~
## $ spectrum_low   <chr> "playful", "shy", "cheery", "masculine", "charming", "l~
## $ spectrum_high  <chr> "serious", "bold", "sorrowful", "feminine", "awkward", ~
## $ is_emoji       <lgl> FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE,~
## $ avg            <dbl> 41.4, 11.1, 22.4, -16.9, 23.1, 3.8, -30.4, -32.8, -24.8~
## $ ratings        <dbl> 51, 63, 78, 71, 72, 60, 76, 74, 72, 70, 63, 67, 59, 70,~
## $ sd             <dbl> 10.9, 27.3, 14.0, 22.3, 25.2, 32.9, 23.7, 20.9, 29.1, 2~
```

```r
unique(Fic_char$gender)
```

```
## [1] "male"   "female" NA
```

```r
unique(Fic_char$spectrum) %>% length()
```

```
## [1] 267
```

```r
unique(Fic_char$spectrum_low) %>% length()
```

```
## [1] 265
```

```r
unique(Fic_char$spectrum_high) %>% length()
```

```
## [1] 265
```

```r
range(Fic_char$ratings)
```

```
## [1]    2 2459
```

I plotted a geom_line graph comparing the ratings and average for each fictional character. I felt like the graph kind of looked like a slinky.


```r
# How much do the ratings vary with avg for each character?
ggplot(Fic_char) +
  geom_line(aes(x = ratings, y = avg, colour = sd))
```

<img src="index_files/figure-html/plot-2-1.png" width="480" />

**Conclusion -The corelation of the ratings varying with the mean of each character.**

## Network - 1

The third dataset that I chose was the Brooklyn-99 data set that my partner and I made. The different columns include Code, Name, Gender, Occupation, Height, personality, type of relationship, etc. 
This dataset helped us make a network connecting all the characters of Brooklyn-99 depending on what kind of relationship they share and how strong that relationship is.


```r
b99_nodes <- read_delim("b99Nodes.csv", delim = ",")
```

```
## Rows: 22 Columns: 6
## -- Column specification --------------------------------------------------------
## Delimiter: ","
## chr (5): Names, Gender, Occupation, Height, personality
## dbl (1): Code
## 
## i Use `spec()` to retrieve the full column specification for this data.
## i Specify the column types or set `show_col_types = FALSE` to quiet this message.
```

```r
b99_nodes
```

```
## # A tibble: 22 x 6
##     Code Names     Gender Occupation Height personality
##    <dbl> <chr>     <chr>  <chr>      <chr>  <chr>      
##  1     1 Jake      m      detective  mid    E          
##  2     2 Amy       f      detective  mid    A          
##  3     3 Gina      f      assistant  mid    E          
##  4     4 Charles   m      detective  short  A          
##  5     5 Holt      m      captain    tall   I          
##  6     6 Terry     m      sergeant   tall   A          
##  7     7 Kevin     m      professor  tall   I          
##  8     8 Cheddar   m      dog        short  E          
##  9     9 Scully    m      detective  tall   A          
## 10    10 Hitchcock m      detective  mid    A          
## # ... with 12 more rows
```

```r
b99_edges <- read_delim("b99Edges.csv", delim = ",")
```

```
## Rows: 60 Columns: 4
## -- Column specification --------------------------------------------------------
## Delimiter: ","
## chr (1): type_of_R
## dbl (3): from, to, weight
## 
## i Use `spec()` to retrieve the full column specification for this data.
## i Specify the column types or set `show_col_types = FALSE` to quiet this message.
```

```r
b99_edges
```

```
## # A tibble: 60 x 4
##     from    to weight type_of_R   
##    <dbl> <dbl>  <dbl> <chr>       
##  1     1     2     13 Dating      
##  2     1     5      9 Professional
##  3     1     3     12 Friend      
##  4     1     4     13 Friend      
##  5     1     6      8 Professional
##  6     1     7      8 Friend      
##  7     1     8      3 Friend      
##  8     1     9      5 Professional
##  9     1    10      5 Professional
## 10     1    11     11 Friend      
## # ... with 50 more rows
```


```r
b99 <- tbl_graph(nodes = b99_nodes, 
                edges = b99_edges, 
                directed = FALSE)
b99
```

```
## # A tbl_graph: 22 nodes and 60 edges
## #
## # An undirected multigraph with 1 component
## #
## # Node Data: 22 x 6 (active)
##    Code Names   Gender Occupation Height personality
##   <dbl> <chr>   <chr>  <chr>      <chr>  <chr>      
## 1     1 Jake    m      detective  mid    E          
## 2     2 Amy     f      detective  mid    A          
## 3     3 Gina    f      assistant  mid    E          
## 4     4 Charles m      detective  short  A          
## 5     5 Holt    m      captain    tall   I          
## 6     6 Terry   m      sergeant   tall   A          
## # ... with 16 more rows
## #
## # Edge Data: 60 x 4
##    from    to weight type_of_R   
##   <int> <int>  <dbl> <chr>       
## 1     1     2     13 Dating      
## 2     1     5      9 Professional
## 3     1     3     12 Friend      
## # ... with 57 more rows
```

We plotted a network to show the different kinds of relationships and the strength of those relationships between the characters of Brooklyn 99. 


```r
ggraph(b99, layout = "linear") +
  geom_edge_arc(aes(width = weight, color = type_of_R), alpha = 0.8) +
  scale_edge_width(range = c(0.2, 2)) + 
  geom_node_point(size = 3, colour = "black") +
  labs(edge_width = "Weight") +
  theme_graph()+
  theme(legend.position = "top")
```

```
## Warning in grid.Call(C_stringMetric, as.graphicsAnnot(x$label)): font family not
## found in Windows font database

## Warning in grid.Call(C_stringMetric, as.graphicsAnnot(x$label)): font family not
## found in Windows font database
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database
```

<img src="index_files/figure-html/plot-3-1.png" width="480" />
**Conclusion - A lot of the characters dislike each other and few are dating/in relationships and quite a few are friends.**

## My Course Reflection

This course was about exploring R as a programming language, understanding it's applications and in turn using it in our work in the future. It was like learning a hack that makes doing a bunch of things easier, especially as aspiring artists and designers.

What I learnt: I learnt that coding isn't so bad after all. In my head it was always like "Ugh coding, sitting in front of a screen all day, not something I want to do", but I actually did end up enjoying a lot of the things we learnt in this course. Apart from the frustrating errors and the fact that the absence of a single comma means the entire code won't run, I realized that coding is actually a shortcut to doing a lot of things that would otherwise take ages to complete. So overall, this course actually changed my view on coding and I'm pretty sure I'm going to use R in the future even though I'm Arvind's VC student :)

How it will help my practice as an aspiring artist and designer: R is capable of doing so much more than I thought. Like Arvind began in the first class, with showing off about R and everything possible with it, I realized that there's really no limit. There's no way that R won't be helpful to artists or designers because it can literally do everything (except be a little more gen z haha). Even though I'm a VC student, I can see myself using R in the future whether it's for plotting a graph to analyse some kind of data or just mapping out how many taco bells have opened up in my city. 

Even though Arvind is a boomer (bleh), He's without doubt my favorite boomer of all time (maybe second favorite after grandma who makes the best chicken biryani, but favorite nonetheless). I've told everyone around me how much I loved being in his class and people are probably fed up of hearing me say it. It felt like being in school again and having a close knit classroom with a teacher that actually cares about us. Thank you Arvind for the endless effort and work you put into your classes, you should know that we really do appreciate it. Thank you for the pep talks, the advice, the chocolates and for setting an example for us. Even though it was only a two week course, I felt like I've known you and everyone in class since forever. I know you said that out of 700 students only 20 kept in touch with you and that we shouldn't feel bad about not keeping in touch, but I promise to be the 21st student in that list. I'm not going to let you forget your VC student. Thanks for the best class ever.

All hail Alice in wonderland 

Jai Hind.
