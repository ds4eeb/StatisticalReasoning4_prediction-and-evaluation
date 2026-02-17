Activity 12: Statistical reasoning 4: prediction and evaluation
================

Welcome! This is the fourth statistical reasoning activity. The goals of
this activity are to understand how to evaluate models and use models to
make predictions. Specifically, you will:

1.  Run and interpret multiple models on the same dataset and evaluate
    them to see which is best supported using WAIC and PSIS.
2.  Use model output to predict how the system will behave with new
    data.

------------------------------------------------------------------------

You will submit one output for this activity:

1.  A **PDF** of a rendered Quarto document with all of your R code.
    Please create a new Quarto document (e.g. don’t use this
    `README.qmd`) and include all of the code that appears in this
    document, your own code, and **answers to all of the questions** in
    the “Q#” sections. Submit this PDF through Gradescope.

A reminder: **Please label the code** in your final submission in two
ways:

1.  denote your answers to each question using headers that correspond
    to the question you’re answering, and
2.  thoroughly “comment” your code: remember, this means annotating your
    code directly by typing descriptions of what each line does after a
    `#`. This will help future you!

------------------------------------------------------------------------

Let’s start by reading in the relevant packages

``` r
library(brms) # for statistics
library(tidyverse) # for data wrangling
library(lterdatasampler)
```

We are going to work with the fiddler crab and latitude data again:

``` r
pie_crab <- lterdatasampler::pie_crab
```

# 1. Model comparison

It is common in the field of ecology to have multiple candidate models
of how a system works. How do we know which is “best”? In this activity
we will learn two metrics that can help: the Watanabe–Akaike information
criterion (**WAIC**) and Pareto Smoothed Importance Sampling (**PSIS**).

Both metrics tell us how well the model will predict data it wasn’t
trained on, which is important for thinking about how well the model
might predict new data (as in the next section!).

| \## 1.1 Run and interpret two different multiple regressions                                        |
|:----------------------------------------------------------------------------------------------------|
| MCSE of elpd_loo is 0.0. MCSE and ESS estimates assume MCMC draws (r_eff in \[0.5, 0.8\]).          |
| All Pareto k estimates are good (k \< 0.7). See help(‘pareto-k-diagnostic’) for details. \`\`\` ::: |
| `{.r .cell-code} loo(m.crab.lat.water)`                                                             |
| ::: {.cell-output .cell-output-stdout} \`\`\`                                                       |
| Computed from 4000 by 392 log-likelihood matrix.                                                    |
| Estimate SE elpd_loo -962.9 13.6 p_loo 3.7 0.3 looic 1925.9 27.2                                    |

MCSE of elpd_loo is 0.0. MCSE and ESS estimates assume MCMC draws (r_eff
in \[0.4, 0.9\]).

All Pareto k estimates are good (k \< 0.7). See
help(‘pareto-k-diagnostic’) for details.

    :::

    ```{.r .cell-code}
    loo(m.crab.lat.air.water)

<div class="cell-output cell-output-stdout">


    Computed from 4000 by 392 log-likelihood matrix.

             Estimate   SE
    elpd_loo   -945.3 14.2
    p_loo         5.0  0.5
    looic      1890.6 28.4
    ------
    MCSE of elpd_loo is 0.0.
    MCSE and ESS estimates assume MCMC draws (r_eff in [0.6, 0.9]).

    All Pareto k estimates are good (k < 0.7).
    See help('pareto-k-diagnostic') for details.

</div>

:::

------------------------------------------------------------------------

# 2. Predictions

------------------------------------------------------------------------

# 3. DIY section

------------------------------------------------------------------------

### Render to PDF

When you have finished, remember to pull, stage, commit, and push with
GitHub:

- Pull to check for updates to the remote branch
- Stage your edits (after saving your document!) by checking the
  documents you’d like to push
- Commit your changes with a commit message
- Push your changes to the remote branch

Then submit the well-labeled PDF on Gradescope. Thanks!
