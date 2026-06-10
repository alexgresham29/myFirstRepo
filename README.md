# myFirstRepo

A learning repository from my summer bootcamp — using GitHub to track R code as I explore statistics and data analysis.

---

## Files

### `analysis.R`

A simple introductory R script that assigns two numbers to variables and performs basic arithmetic on them.

```r
x <- 3
y <- 4
x * y   # returns 12
```

This was the first file in the repo — a starting point for getting comfortable with R syntax and GitHub.

---

### `sampling_distribution.Rmd`

An R Markdown notebook that demonstrates the **Central Limit Theorem (CLT)** through simulation. The CLT is one of the most important results in statistics: it says that no matter how strange or skewed a population is, the *average* of a random sample from that population will follow a normal (bell-shaped) distribution as the sample size grows.

**What the notebook does, step by step:**

1. **Builds a non-normal population** — a right-skewed mixture of 100,000 values designed to look nothing like a bell curve, so the CLT's effect is clearly visible.

2. **Runs 1,000 simulations** at three sample sizes:
   - Small (n = 5)
   - Medium (n = 30)
   - Large (n = 100)

   Each simulation draws a random sample of size n, computes its mean, and records it. After 1,000 repetitions we have 1,000 sample means — the *sampling distribution*.

3. **Visualises the results** using `ggplot2`:
   - A histogram of the raw population (showing how skewed it is)
   - Faceted histograms of sample means at each sample size, with a theoretical normal curve overlaid
   - An overlay plot showing all three sampling distributions on the same axes
   - Q-Q plots checking how closely the sample means follow a normal distribution

4. **Verifies the Standard Error formula** — the spread of the sampling distribution follows σ/√n exactly, confirmed by comparing observed standard errors from the simulation to the theoretical values.

**Key takeaway:** At n = 5, the distribution of sample means is still noticeably skewed. By n = 30 it looks approximately normal. By n = 100 it matches the theoretical normal curve almost perfectly.

### `sampling_distribution.nb.html`

The rendered HTML output of the notebook above — open this file in a browser to read the full analysis with all plots and explanations without needing to run any R code.

### `notebook_style.css`

Custom CSS that styles the HTML notebook with elegant typography (Playfair Display headings, Source Serif 4 body text, Fira Code for code blocks) and styled callout boxes.

---

## How to run the notebook

You need R with the following packages installed:

```r
install.packages(c("rmarkdown", "ggplot2", "dplyr", "tidyr", "knitr"))
```

Then open `sampling_distribution.Rmd` in RStudio and click **Run All**, or render it from the terminal:

```r
rmarkdown::render("sampling_distribution.Rmd")
```
