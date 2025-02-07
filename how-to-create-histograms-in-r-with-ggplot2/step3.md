# Build a Histogram

We're going to use `ggplot2::geom_histogram()` to view the distribution the `stars` variable in `Ramen`.

Note that we are also assigning labels to the graph that includes a clear title, descriptive information about the graph, and the source of the data:

```
# click to execute code
gg_step3_hist_01 <- Ramen %>%
  ggplot(aes(x = stars)) +
  geom_histogram() +
  labs(
       title = "Distribution of ramen stars",
       subtitle = "bins = 30",
       caption = "source: https://www.theramenrater.com/resources-2/the-list/")
# save
ggsave(plot = gg_step3_hist_01,
        filename = "gg-step3-hist-01.png",
        device = "png",
        width = 9,
        height = 6,
        units = "in")
```{{execute}}

Let's view the graph we just created; open _gg-step3-hist-01.png_ in the VS Code IDE above the Terminal console to view the graph.

As we stated above, histograms stack the variable values into a defined set of `bins`. The default number for `bins` is `30`. We can change the shape of the histogram by changing the `bins` argument.
