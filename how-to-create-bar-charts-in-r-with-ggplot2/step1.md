### Initiate R

Launch an R console by clicking here: `R`{{execute}}.


### Load packages

The package we'll use to view the entire dataset with R is [`skimr`](https://docs.ropensci.org/skimr/). We will install and load the following packages:


```
install.packages(c("tidyverse", "skimr"))
library(tidyverse)
library(skimr)
```{{execute}}

## Navigating Katacoda

Let's take a quick tour of our Katacoda environment. In the following steps, we'll be running code, viewing output, and creating graphs. To accomplish this, we'll need to understand what tools are at our disposal.

### Sidebar

You're reading this in the **Sidebar**. All of the instructions are in the Sidebar, and at the bottom, you'll find a "*Continue*" button to take you to the next step. See the image below:


![](https://raw.githubusercontent.com/mjfrigaard/katacoda-scenarios/master/how-to-create-bar-charts-in-r-with-ggplot2/img/sc-03-sidebar.png)



### Code blocks

You will also find **code blocks** in the Sidebar. All the code blocks will run when you click on them (you've already run a few above!). See the image below for more examples:


![](https://raw.githubusercontent.com/mjfrigaard/katacoda-scenarios/master/how-to-create-bar-charts-in-r-with-ggplot2/img/sc-03-code-blocks.png)

<h3>Terminal</h3>

The *Terminal* is where the R code from each code block will run, along with any text **output**. We can also use R interactively by typing them directly into the Terminal after the **Prompt `>`**.

Go ahead and try it by typing (or copying and pasting) the following commands:

```
tidyverse::tidyverse_logo()
```{{execute}}

You should see the following output in the **Terminal**:


![](https://raw.githubusercontent.com/mjfrigaard/katacoda-scenarios/master/how-to-create-bar-charts-in-r-with-ggplot2/img/sc-03-terminal-code.png)


### VS Code (Explorer)

When we create graphs, we will include the `ggplot2::ggsave()` function in the code block. This function allows us to save the graph image as a `.png` file in the *VS Code Explorer*.

### VS Code (ROOT)

Inside the VS Code explorer, you'll find a section labeled *ROOT.* _ROOT_ is a folder that contains our new graph files. We can open the *Graph file* by clicking on them. See the image below for an example:


![](https://raw.githubusercontent.com/mjfrigaard/katacoda-scenarios/master/how-to-create-bar-charts-in-r-with-ggplot2/img/sc-03-explorer-root.png)

The image below gives you an overview of this entire process:


![](https://raw.githubusercontent.com/mjfrigaard/katacoda-scenarios/master/how-to-create-bar-charts-in-r-with-ggplot2/img/sc-03-code-run-png-view.png)


Now that we know how to navigate the Katacoda environment, we can start exploring data and building graphs!
