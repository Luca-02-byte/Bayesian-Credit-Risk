# Bayesian Credit Risk

Project for the *Applied Statistical Modelling* course, Master's in Economics and Data Analysis | Data Science curriculum, Università degli Studi di Bergamo.

## Course Context

Applied Statistical Modelling covers Bayesian inference and computational methods for applied statistics, with a focus on Markov Chain Monte Carlo (MCMC) techniques implemented in [NIMBLE](https://r-nimble.org/) (R). The course combines theoretical foundations (hierarchical models, Gibbs sampling, convergence diagnostics) with hands-on implementation on real datasets.

## Project Overview

This project applies **Stochastic Search Variable Selection (SSVS)** — a Bayesian variable selection method based on spike-and-slab priors — to a logistic regression model for **loan default prediction**.

**Key questions addressed:**
- Which borrower and loan characteristics are genuinely associated with default risk?
- How strong and uncertain are these effects?
- How well does the resulting model predict default on unseen data?

**Method**: each regression coefficient is assigned a two-component Gaussian mixture prior (a narrow "spike" near zero for irrelevant predictors, a diffuse "slab" for relevant ones), with inclusion governed by latent indicators estimated via Gibbs sampling in NIMBLE.

**Dataset**: [Credit Risk Dataset](https://www.kaggle.com/datasets/laotse/credit-risk-dataset) (Kaggle, by *laotse*) — 32,581 loan applications; after cleaning, n = 28,632 observations and 13 candidate predictors.

**Results**: 11 of 13 predictors are selected (Median Probability Model); the strongest effects are home ownership and prior default history. The selected model achieves an AUC of 0.806 on a held-out test set, and separates clearly between illustrative low-risk (~1–2% predicted default probability) and high-risk (~66%) borrower profiles.



## Contents

- [`report.pdf`](./Report+Code.pdf) — full written report with commented code

- [`slides.pdf`](./Slides_BCR.pdf) — presentation slides for the oral exam

## Tools

R, [NIMBLE](https://r-nimble.org/), `MCMCvis`, `coda`, `tidymodels` , LaTeX.
