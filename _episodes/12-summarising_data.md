---
title: "Summarising Data"
teaching: 5
exercises: 0
questions:
- "How do I summarise categorical data?"
- "How do I summarise continuous data?"
objectives:
- "Learn how to ucalculate descriptive statistics"
- "Learn how to produce frequency tables"
keypoints:
- "Thwe way we summarise and plot data depends on the data type."
---

## How do I summarise categorical data?
Categorical data can be summarised as a frequency table. For example we can produce a frequency table for the different species:
~~~
> penguins %>% 
>  + count(species) 
~~~

~~~
# A tibble: 3 × 3
# Groups:   species [3]
  species       n  prop
  <fct>     <int> <dbl>
1 Adelie      152     1
2 Chinstrap    68     1
3 Gentoo      124     1
~~~

For nominal data like this there is very little else we can do. Let's move on to the continuous variables.

## How do I summarise continuous data?
Continuous (numerical) data can be summarised using an array of descriptive statistics including measures of central tendency (e.g. mean, median, and mode) and measures of spread (e.g. standard deviation and inter-quartile range).

Try getting the means for each species:
~~~
> penguins %>% 
> +   group_by(species) %>% 
> +   summarize(across(where(is.numeric), mean, na.rm = TRUE))
~~~
~~~
# A tibble: 3 × 6
  species   bill_length_mm bill_depth_mm flipper_length_mm body_mass_g  year
  <fct>              <dbl>         <dbl>             <dbl>       <dbl> <dbl>
1 Adelie              38.8          18.3              190.       3701. 2008.
2 Chinstrap           48.8          18.4              196.       3733. 2008.
3 Gentoo              47.5          15.0              217.       5076. 2008.
~~~


