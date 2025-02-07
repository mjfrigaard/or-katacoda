# Visualizing a Numerical and Categorical Variable

Boxplots are also great for visualizing continuous variables across the levels of a categorical variable. For example, we have the `Balance` dataset with `value`s of European Union countries' budget surplus. We can add the categorical variable to the `y` axis to view one boxplot per `country` level:

```
# click to execute code
# the data
Balance %>%
    ggplot2::qplot(x = value, y = country,
                    data = ., geom = "boxplot")
ggsave(filename = "gg-step7-box.png", device = "png",
        width = 7, height = 5, units = "in")
```{{execute}}

Click on the _gg-step7-box.png_ file in _ROOT_ folder above. For more on the statistics displayed in the boxplot, read up on the [`geom_boxplot()` documentation](https://ggplot2.tidyverse.org/reference/geom_boxplot.html).

Other options for individual variables include the [`geom = "density"`](https://ggplot2.tidyverse.org/reference/geom_density.html) and [`geom = "violin"`](https://ggplot2.tidyverse.org/reference/geom_violin.html).

## Visualizing Two Continuous Variables

What if we want to graph the relationship between two variables? In this step, we'll graph two variables from the `Brexit` dataset. Use the terminal to view this dataset with `dplyr::glimpse()` or `utils::str()`.

When we view the contents of `Brexit`, we can see the `date` column is a character variable (`<chr>`), and the other two variables&mdash;`percent_responding_right` and `percent_responding_wrong`&mdash;are numeric (`<dbl>`).

### Creating Date Variables

If we want to plot the relationship between `date` and the `percent_responding_right`, we'll first need to change the format of `date` from character to `Date`, which we can do using the [`lubridate` package](https://lubridate.tidyverse.org/) (also from the `tidyverse`).

Copy the following code and complete the `lubridate::mdy()` function to format the `date` variable as a `Date`:

```
# click to copy code
# first reformat the date variable as a date
Brexit <- Brexit %>% mutate(date = lubridate::dmy(____))
```{{copy}}

<!-- The code below uses the `lubridate::mdy()` function to format the `date` variable as a `Date`.

```
# click to execute code
# first reformat the date variable as a date
Brexit <- Brexit %>% mutate(date = lubridate::dmy(date))
```{{execute}} -->

Read more about `dmy()` [here.](https://lubridate.tidyverse.org/reference/ymd.html)

Use the `base::is.double()`, `base::class()`, or `base::typeof()` function to figure out if you've formatted the new `date` variable correctly:

```
# click to execute code
base::is.double(Brexit$date)
base::class(Brexit$date)
base::typeof(Brexit$date)
```{{execute}}

You should see the following output in the Terminal:

```
> base::is.double(Brexit$date)
[1] TRUE
> base::class(Brexit$date)
[1] "Date"
> base::typeof(Brexit$date)
[1] "double"
```

After we're sure we've formatted the `date` variable correctly, we want to `pipe` the formatted data to the `ggplot2::qplot()` function with the new `date` variable on the `x` and the `percent_responding_right` variable on the `y`:

```
# click to execute code
Brexit %>%
    qplot(x = date,
          y = percent_responding_right, data = .)

ggsave(filename = "gg-step7-point.png", device = "png",
        width = 7, height = 5, units = "in")
```{{execute}}

Click on the _gg-step7-point.png_ file in _ROOT_ above to view the output.

The `ggplot2::qplot()` function is smart enough to automatically choose a `geom` depending on what type of variable we assign to the `x` and `y` axes. In this case, the `percent_responding_right` variable is a `<dbl>` (numeric), and we've reformatted the `date` variable into a double before we passed it to the `y` axis.

The `ggplot2::qplot()` function knows to plot the dates on the `y` axes (notice it displays only the `year`) and represent the data with `geom = "points"`.
