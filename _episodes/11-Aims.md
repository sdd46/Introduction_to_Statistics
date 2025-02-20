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
During this session we will use a dataset on penguin characteristics measured at the Palmer Station in Antarctica. Install and load this dataset using the code below:
~~~
install.packages("palmerpenguins")
data(package = palmerpenguins)
library(palmerpenguins)
~~~
