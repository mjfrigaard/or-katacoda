Setup
================

This `README` covers how to set up a scenario for Katacoda (from O'Reilly) and some tips for using the Katacoda interface.

## Step 1: Downloading CLI for Katacoda

First download the installation pack from Terminal:

```bash
npm install katacoda-cli --global
```

## Step 2: Documentation for Katacoda Scenarios

After receiving the Katacoda invite email, you can log into Katacoda with a Github account.

For example, the url for my account is created (`https//:katacoda.com/mjfrigaard`). The link for the Katacoda documentation is [here](https://www.katacoda.com/docs).

## Step 3: Create local repo for scenario

I used the following steps in the Terminal:

```bash
$ katacoda scenarios:create
? Friendly url:  katacoda-scenarios
? Scenario Title:  title the scenario
? Scenario Description:  description of the scenario, displayed on the intro screen
? Difficulty Level: provide users with a sense of the depth of content, displayed on the intro screen
? Estimated time: provide users with an estimated time to complete, displayed on the intro screen
? Number of Steps (Not including intro & finish):  the numbers of the steps that the scenario will have. The CLI will create all the template files for all the steps that you specified
? Image:  katacoda.com/docs/scenarios/environments
? Layout: katacoda.com/docs/scenarios/layouts  (`Terminal + Editor for the embedded presentation`)

Scenario created successfully.
```

This creates the following folder contents:

```bash
├── name-of-scenario
    ├── finish.md
    ├── index.json
    ├── intro.md
    ├── step1.md
    ├── step2.md
    ├── step3.md
    ├── step4.md
    └── step5.md
```

## Step 4: Configure Github repository

Create a new repository on Github, **without a README**, like the one located here:

The webhook setup is covered in multiple places. [Here is the official Katacoda documentation](https://katacoda.com/docs/configure-git), but I've also included a [Google Document](https://docs.google.com/document/d/e/2PACX-1vSf2w2onhH5t3IhuD4sYLoWqn46BLKMYFR7q3BHO8QTaRkVgXfhKvnl8T9uHrjmbVpTZVKCWrfxEl0R/pub) that outlines this process (with ample screenshots).

### On the Katacoda end...

The important parts of the configuration for Katacoda are:

Under the **Git Scenario Repository**, enter the repository from Github:

`https://github.com/mjfrigaard/name-of-repo`

Then click **Save** and **Trigger**. You should see the **Deployed Successfully** come across the screen. I clicked refresh to get the **Git Webhook Secret**. Under the **Git Webhook Secret**, enter the

`jumbletextnumbers`

### The Github end...

The important parts of the configuration for Github are:

**Payload URL:** `https://editor.katacoda.com/scenarios/updated`

**Content type:** `application/json`

**Secret:** `jumbletextnumbers`

After entering this information, you should get this message from Github,

*Okay, that hook was successfully created. We sent a ping payload to test it out! Read more about it at https://developer.github.com/webhooks/#ping-event.*

## Step 5: Push the changes to Github

After creating this repo (without a `README.md` file), I was able to enter the following code into the command line and set the remote.

These commands were used to set up the Gitub repo.

```bash
git init
git add -A
git commit -m "first commit"
```

Now I could add the remote/origin.

```bash
# …or push an existing repository from the command line
git remote add origin https://github.com/mjfrigaard/katacoda-data-wrangle-viz-show.git
git push -u origin master
```

***

## Appendix 1: Katacoda scenario tutorials

The tutorial for building the scenario is [here](https://katacoda.com/scenario-examples/scenarios/create-scenario-101).

I took notes on this tutorial and made them available in [this Google document](https://docs.google.com/document/d/e/2PACX-1vSf2w2onhH5t3IhuD4sYLoWqn46BLKMYFR7q3BHO8QTaRkVgXfhKvnl8T9uHrjmbVpTZVKCWrfxEl0R/pub).

## Appendix 2: Katacoda guidelines

There are multiple guidelines and resources for writing scenarios. O'Reilly has provided an *Authoring Guide* and *Formatting and Design Guide*.

The link for these files can be found here:

+ [Katacoda Scenario Formatting and Design Guide for Authors](https://docs.google.com/document/d/1l4lofG5kAu8JFzumZPCsJJE2muCYe6rHSHCQsMlijd8/edit)

+ [Katacoda Scenario Authoring Guide](https://docs.google.com/document/d/14rudtruZQhRxvD3zcR3g75j5nuOgKGz4CYk8hdhaV-w/edit)

## Appendix 3: Scenario Checklist

**Scenario Readiness Checklist:**

When you think your scenario is ready for publication, we recommend you run through the checklist below to ensure it is ready to go. [Reminder: We discuss these best practices in the Katacoda Formatting and Design Guide for Authors]:

Does the scenario start consistently and in a timely manner? More than 5 minutes to start would be cause to reconsider your build decisions.

- [ ] Are your intro and final pages present and are their respective goals and lessons learned in agreement?

- [ ] Have you tested your scenario lately?

- [ ] Do you agree with the leveling (beginner, intermediate, advanced) you indicated when you started the build?

- [ ] Was learning time you entered correct, or should it be adjusted?

- [ ] Are your versions of tools and other dependencies up to date?

- [ ] Have you tried every instruction?

- [ ] Have you written each step in the most concise manner possible?

- [ ] Have you run your text through a spelling/grammar checker?

- [ ] Are your credits to others given present and correct?

- [ ] Are your images legal and with credits?

- [ ] Are your hyperlinks all working?

- [ ] Do the goals and lessons learned items match the steps in the scenario?


## R Environments

The Katacoda team recently rebuilt the R image, so I wanted to let you know that the latest-greatest R image you should be using in your Katacoda scenarios is `rlang:3.4`


~~~

```r
Launch the REPL via `R`

An example function in R is `hello<-function() cat("Hello, world!\n")`

This can be called from the command line `hello()`

To display a plot, ensure you call `dev.off()` function.

More demos are available with `demo()`

```

~~~

