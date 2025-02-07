# Getting Your Data Into the Correct Shape

We rarely collect data in a way that can be immediately analyzed or visualized. "Wrangling," "munging," or "cleaning" are the steps to prepare data for a table, graph, algorithm, or model. These terms might sound like they're referring to tedious, menial work, but data wrangling is such a common task that most data scientists [consider it up to 80% of their job](https://www.nytimes.com/2014/08/18/technology/for-big-data-scientists-hurdle-to-insights-is-janitor-work.html).

## Goals & Lessons

This scenario will introduce the following topics in R:

1. How to get data into R (manually, importing rectangular files, from packages)
2. How to use R to reshape (or *reformat* and *reshape*) your data (pivot functions)
3. How to create new variables based on existing columns
4. How to create new variables based on conditions (i.e., the values in existing columns)
5. How to check your work with pivoting

## The tidyverse

In this scenario, we'll be using the [`tidyverse packages`](https://www.tidyverse.org/), which are "an opinionated collection of R packages designed for data science."
