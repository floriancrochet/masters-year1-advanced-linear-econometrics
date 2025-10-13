# Analyse économétrique de l’impact de la gestion budgétaire sur la réussite académique  
*An econometric analysis of financial management effects on students’ academic performance.*

---

## 📘 Overview
This project investigates the **impact of students’ financial behavior on their academic performance**, using econometric modeling applied to survey data collected from students in Loire-Atlantique (France) during the **2023–2024 academic year**.  

Developed as part of the **Master 1 in Econometrics and Statistics – Applied Econometrics track**, the project explores how financial stress, spending habits, and budget management influence students’ grade point averages.

**Objectives**
- Identify key financial, social, and academic determinants of academic success  
- Apply linear econometric modeling with diagnostic and robustness tests  
- Evaluate the predictive performance of the estimated model  
- Provide policy recommendations to reduce financial stress among students  

---

## ⚙️ Features
- Comprehensive data analysis (univariate, bivariate, multivariate)  
- Linear regression models with OLS and 2SLS estimations  
- Automatic variable selection (stepwise)  
- Instrumental variable approach to correct endogeneity  
- Hypothesis testing: normality, heteroskedasticity, multicollinearity, and specification  
- Visualization of distributions and diagnostic plots  

---

## 🧰 Tech Stack
**Language:** R  
**Libraries:** `tidyverse`, `MASS`, `car`, `lmtest`, `AER`, `PerformanceAnalytics`, `ggplot2`, `sjPlot`, `corrplot`, `EnvStats`, `leaps`, `openxlsx`  

---

## ⚙️ Installation
Clone the repository and open the R project:

```bash
git clone https://github.com/À compléter/gestion-budget-etudiants.git
cd gestion-budget-etudiants
```

Install dependencies in R:
```R
install.packages(c("tidyverse", "MASS", "car", "lmtest", "AER", 
                   "PerformanceAnalytics", "ggplot2", "sjPlot", 
                   "corrplot", "EnvStats", "leaps", "openxlsx"))
```

---

## 📚 Usage Example

```r
library(openxlsx)
library(AER)

# Import dataset
Budget <- read.xlsx("data/budget.xlsx")

# Fit linear model
model <- lm(MOYENNE ~ ASSIDUITE + STRESS + RESTAURANT + AGE, data = Budget)
summary(model)

# Two-Stage Least Squares example
iv_model <- ivreg(MOYENNE ~ STRESS | CAF + LOGEMENT + SOMMEIL, data = Budget)
summary(iv_model)
```

---

## 📂 Project Structure

```
budget-etudiants/
│
├── data/               # Questionnaire responses (budget.xlsx)
├── src/                # R scripts for analysis and modeling
├── notebooks/          # RMarkdown reports
├── results/            # Regression outputs and plots
├── requirements.R      # Required R packages
└── README.md
```

---

## 📊 Results
The econometric analysis highlights that:
- **Financial stress** negatively impacts academic performance.  
- **Working while studying** and **frequent restaurant visits** are associated with lower averages.  
- **Tutoring, scholarships, and financial support** have a positive effect.  
- **Instrumental variables** (CAF, rent, Uber Eats usage, etc.) effectively correct endogeneity in stress-related variables.  

Example output (after outlier correction):
> Most students achieved an average above 12.06/20, with financial and academic factors explaining a significant portion of this variation.

![Example Results](./assets/example_forecast.png)

---

## 🧠 References
For theoretical background:
- Lassarre, D., Giron, C., & Paty, B. (2003). *Stress des étudiants et réussite universitaire*.  
- Verley, E. & Zilloniz, S. (2011). *Fragilités économiques, fragilités studieuses.*  
- Hamilton, J.D. (1994). *Time Series Analysis*.  
- Wooldridge, J.M. (2019). *Introductory Econometrics: A Modern Approach*.  
- Hyndman, R.J. & Athanasopoulos, G. (2018). *Forecasting: Principles and Practice.*

---

## 📜 License
This project is released under the **MIT License**.  
© 2025 Pierre Quintin de Kercadio & Florian Crochet  

---

## 👤 Authors
**Pierre QUINTIN DE KERCADIO**  
🔗 [LinkedIn](https://www.linkedin.com/in/pierre-quintin-de-kercadio/)  

**Florian CROCHET**  
🔗 [LinkedIn](https://www.linkedin.com/in/floriancrochet/)  

*Master 1 – Econometrics & Statistics, Applied Econometrics Track*  

---

## 💬 Acknowledgments
We thank the students who participated in the survey and the academic community for providing methodological guidance.
