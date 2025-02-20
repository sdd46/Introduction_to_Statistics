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
- "You will get stuck at some point, needing help is a case of when not if."
- "Help is available, but it is important you have done your due diligence and are asking for help in the correct places and in the correct format."
---

## How do I summarise categorical data?
Categorical data can be summarised as a frequency table. For example we can produce a frequency table for the different species:
~~~
penguins %>%
  count(species) %>%
  group_by(species) %>%          
  mutate(prop = prop.table(n))
~~~


