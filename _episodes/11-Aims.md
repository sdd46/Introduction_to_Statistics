---
title: "Introduction to Statistics"
teaching: 5
exercises: 0
questions:
- "How do we import data into RStudio?"
- "How do we summarise different types of data?"
- "How do we plot data?"
objectives:
- "Be able to import data into RStudio"
- "Be confident summarising different types of data"
- "Be able to produce a range of different types of plots"
keypoints:
- "R and RStudio are not the same thing. RStudio is an IDE that provides you with a convenient way to manage R projects and R is the underlying language that enables RStudio."
- "You will not learn everything about R or RStudio in a day, there are a huge number of tools available to you in RStudio. The more time you commit to exploring and practicing the more you will achieve."
- "Project management is a vital part of ensuring that you are producing maintainable, sharable, and robust software."
---

## Starting a new project:
>Let us start by exploring the major features we will use for this course in RStudio. Our first aim is to become more familiar with the interface.  
>Start by generating a new project (name it **‘OneZooStatsT’**).  
>Next, open a new script file (name it **'1-Introduction’**).  
>  
>**Instructions**  
>* From the main menu select **‘File’ > ‘new project’ > ‘new directory’ > ‘new project’**.   
>* You will be prompted for a directory name for your project and a file path where you want to create the project.   
>* Name your project “OneZooStats" and choose the folder you previously created as part of your set-up worksheet.  
>* Open a new script using the small green plus button above the top left pane.  

{% include figure.html max-width="100%" file="/fig/rstudioIDE.png" 
alt="RStudio pane layout on first initialisation" caption="Figure 1: RStudio layout you should expect to see (OS and version dependant)" %}

## Data import 
During this session we will use a dataset on penguin characteristics measured at the Palmer Station in Antarctica (Horst et al., 2020). Install and load this dataset using the code below:
~~~
install.packages("palmerpenguins")
data(package = palmerpenguins)
library(palmerpenguins)
~~~

Let's inspect the data:
~~~
> head(penguins)

# A tibble: 344 × 8
   species island    bill_length_mm bill_depth_mm flipper_length_mm body_mass_g sex   
   <fct>   <fct>              <dbl>         <dbl>             <int>       <int> <fct> 
 1 Adelie  Torgersen           39.1          18.7               181        3750 male  
 2 Adelie  Torgersen           39.5          17.4               186        3800 female
 3 Adelie  Torgersen           40.3          18                 195        3250 female
 4 Adelie  Torgersen           NA            NA                  NA          NA NA    
 5 Adelie  Torgersen           36.7          19.3               193        3450 female
 6 Adelie  Torgersen           39.3          20.6               190        3650 male  
 7 Adelie  Torgersen           38.9          17.8               181        3625 female
 8 Adelie  Torgersen           39.2          19.6               195        4675 male  
 9 Adelie  Torgersen           34.1          18.1               193        3475 NA    
10 Adelie  Torgersen           42            20.2               190        4250 NA    
# ℹ 334 more rows
# ℹ 1 more variable: year <int>
# ℹ Use `print(n = ...)` to see more rows
~~~

Here we can see that some of the rows contain missing data. Let's remove these before we go any further:
~~~
penguins = penguins %>%
  filter(!is.na(bill_length_mm))
~~~

This dataset contains seven variables: three categorical nominal variables (species, island and sex) and four numerical continuous variables (bill_length_mm, bill_depth_mm, flipper_length_mm and body_mass_g). On the next page we will examine how to summarise these different variables.

#Reference List
Horst AM, Hill AP, Gorman KB (2020). palmerpenguins: Palmer Archipelago (Antarctica) penguin data. R package version 0.1.0. https://allisonhorst.github.io/palmerpenguins/. doi: 10.5281/zenodo.3960218.
