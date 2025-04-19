
# 🧠 7089CEM: Statistical Methods for Data Science

This repository contains a complete analysis of MEG brain response data from a simulated neuromarketing experiment. The project combines nonlinear regression modelling and Bayesian inference techniques to investigate how the brain reacts to emotional versus neutral audio stimuli.

---

## 📁 Repository Structure

| File/Folder | Description |
|-------------|-------------|
| `SMDS_CW.R` | Main R script with structured code for data processing, modeling, and ABC |
| `data/` | Contains raw input files: `X.csv`, `y.csv`, and `time.csv` |

---

## 📊 Task 1: Exploratory Data Analysis (EDA)

### 🎯 Objective  
Understand the structure and patterns in MEG responses under emotional and neutral audio stimuli.

### 📈 Visualizations  
- Time series of MEG and audio signals  
- Histograms, boxplots, and scatter plots by stimulus type  
- Pearson correlation analysis

> **Insight:** Emotional narration resulted in higher and more varied MEG responses, justifying a nonlinear modelling approach.

---

## 🔁 Task 2: Nonlinear Regression Modelling

### 🧮 Models Evaluated  
- Five polynomial regression models of varying complexity  
- Estimated using least squares  
- Evaluated using RSS, Log-Likelihood, AIC, BIC, and residual diagnostics

### 🧠 Best Model: Model 3  
Polynomial terms: `x1, x1², x1⁴, x2`  
Demonstrated best balance between fit and generalization.

### 🧪 Results Summary

| Model | RSS | AIC | BIC | Residual Normality |
|-------|-----|-----|-----|--------------------|
| Model 3 | ✅ Lowest | ✅ Best | ✅ Best | ✅ Good fit |
| Model 4 | Close | Slightly worse | Acceptable | Also valid |
| Others | ❌ Poor fit | ❌ Higher error | ❌ Deviations | ❌ Skewed residuals |

> **Conclusion:** Model 3 best captures the nonlinear brain response to audio stimuli.

---

## 📦 Task 3: Approximate Bayesian Computation (ABC)

### 🔍 Goal  
Estimate uncertainty in the top two most influential model parameters of Model 3.

### 🔧 Method  
- Rejection sampling ABC  
- Uniform priors (±30%) around least squares estimates  
- 10,000 simulations; top 1% used to form posterior

### 📊 Outcomes  
- Marginal and joint posterior distributions  
- Parameters show weak correlation, but strong identifiability  
- Posterior centers align closely with initial estimates

> **Insight:** ABC confirmed robustness of Model 3 and provided interpretable uncertainty quantification.

---

## ✨ Key Takeaways

- Emotional voice triggers stronger brain activity measurable by MEG.
- Nonlinear regression (Model 3) provides best fit for input-output relationship.
- ABC is a powerful tool to quantify uncertainty in complex models without explicit likelihoods.

---

## 🧑‍💻 Author

**Itorobong Akpan**  
MSc Data Science & Computational Intelligence  
Coventry University, UK  
📧 akpani4@uni.coventry.ac.uk  
🔗 [GitHub Profile](https://github.com/akpanitorobong)

---
