# Actuarial R Tutorials

Worked R notes for actuaries who need a GLM to land in Excel.

**Live notes:** https://sdcastillo.github.io/Actuarial-R-Tutorials/

Actuarial R Tutorials is a worked note on taking a generalized linear model fitted in R and deploying it as an Excel formula. The tutorial, *Excelerating the Production Pipeline*, writes the coefficients and the R predictions into a workbook, then rebuilds the mean in a spreadsheet cell so the same numbers can be checked without opening R.

The notes are for actuaries, exam candidates, and analysts who estimate in R and review in Excel. The example is deliberately small: petal width on the iris data, with a Gaussian family, a log link, and one log-transformed covariate. The four steps are the same ones you would use for a pricing or reserving GLM.

Open the rendered tutorial, or rerun `Convert R GLM to Excel.Rmd`. Load tidyverse, broom, openxlsx, and kableExtra; fit `glm(Petal.Width ~ Sepal.Width + log(Petal.Length), family = gaussian(link = "log"))`; write the coefficient table and `predict(..., type = "response")` into `R GLM in Excel.xlsx`; then enter `=EXP(coefficients!$B$2+coefficients!$B$3*[@[Sepal.Width]])*[@[Petal.Length]]^coefficients!$B$4` and confirm the new column matches `predicted_petal_width`.

That formula is the log link solved for the mean. From `log(Y) = β0 + β1 X1 + β2 log(X2)` the cell is `exp(β0 + β1 X1) × X2^β2`, and each beta is read from the coefficients sheet. On this fit those values are about −1.835, 0.053, and 1.369. Keeping them in cells means a refit updates the workbook without retyping constants. The same export covers other `glm` families; a logistic model uses `family = binomial(link = "logit")`.

Sam Castillo wrote the tutorial in 2019 while studying mathematics at UMass Amherst. This repository keeps that note — the R Markdown, the notebook render, the sample workbook, and the Excel screenshots. People working on the project now add further notes through `_data/tutorials.yml` and add their names in `_data/people.yml`.

## What you can take from it

- A four-step path from an R `glm` to a checked Excel formula.
- A coefficient sheet so production numbers stay tied to the latest fit.
- Log-link algebra reduced to `EXP` and a power for log-transformed inputs.
- A published iris example, with the estimates stored beside the R predictions.
- The same export pattern for other GLM families, including logistic regression.
- The prettydoc page, the R notebook, the `.Rmd` source, and `R GLM in Excel.xlsx`.

## Files

- [Excelerating the Production Pipeline](Convert_R_GLM_to_Excel.html) — rendered prettydoc
- [Notebook render](Convert%20R%20GLM%20to%20Excel.nb.html)
- [R Markdown source](Convert%20R%20GLM%20to%20Excel.Rmd)
- [Sample workbook](R%20GLM%20in%20Excel.xlsx)

## Working on this

Add a tutorial by appending `_data/tutorials.yml`. Add your name in `_data/people.yml`. The steps are in [CONTRIBUTING.md](CONTRIBUTING.md).

Part of [SamWiki](https://sdcastillo.github.io/samwiki/).
