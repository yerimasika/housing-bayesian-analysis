# Advanced Bayesian Analysis – California Housing Prices

This repository presents an **advanced Bayesian analysis project** focused on modeling and predicting **median housing prices in California**.  
The project explores multiple Bayesian regression models to capture uncertainty, non-normality, asymmetry, and multimodality in real estate prices.

It was developed as part of an **advanced Bayesian statistics course** within a Master’s degree in Data Science and Economics.

---

## Project Objective

Housing prices exhibit:
- strong heterogeneity across regions,
- heavy-tailed distributions,
- asymmetry and extreme values,
- and complex relationships with socio-economic and geographic factors.

The goal of this project is to:
- model housing prices using **Bayesian regression techniques**,
- explicitly quantify **uncertainty** around parameters and predictions,
- compare different likelihood assumptions,
- and identify the most robust model using Bayesian model comparison.

---

## Dataset

- **Source**: California Housing Dataset
- **Observations**: ~20,000 census block groups
- **Target variable**: `median_house_value`
- **Key features**:
  - Median income
  - Housing median age
  - Number of households
  - Ocean proximity (categorical)
  - Demographic and structural indicators

Missing values are removed and extreme outliers are filtered to improve robustness.

---

## Methodology

### 1. Exploratory Data Analysis
- Descriptive statistics
- Correlation analysis and multicollinearity detection
- Geographical visualization of housing prices
- Identification of heavy tails and skewed distributions

### 2. Feature Selection
- Removal of highly collinear variables
- Selection based on economic relevance and statistical significance
- Encoding of categorical variables (`ocean_proximity`)

### 3. Bayesian Regression Models

Multiple Bayesian models are implemented using **PyMC**:

- Linear regression with **Normal likelihood**
- Poisson regression
- Linear regression with **SkewNormal likelihood**
- **Student-t regression** (robust to outliers)
- **Skewed Student-t regression**
- **Bimodal mixture models**
- Mixture of **Skewed Student-t distributions**

Each model is estimated via **MCMC (NUTS sampler)**.

---

## Model Comparison

Models are compared using:
- **LOO cross-validation (elpd_loo)**
- Effective number of parameters (p_loo)
- Convergence diagnostics (R-hat, ESS)
- Posterior predictive checks (PPC)

### Best-performing model
- **Skewed Student-t regression**
- Weight ≈ **92%** probability of being the best model
- No major convergence or robustness warnings

---

## Results & Interpretation

- Median income is the strongest positive predictor of housing prices
- Inland locations are associated with significantly lower prices
- Bayesian R² ≈ **0.50**, indicating meaningful explanatory power
- Posterior predictive checks show good alignment with observed distributions
- Bayesian framework allows clear interpretation via **credible intervals**

---

## Technologies Used

- Python
- PyMC
- ArviZ
- Pandas / NumPy
- Scikit-learn
- Matplotlib / Seaborn
- Jupyter Notebook

---

## Repository Structure
```
├── Code/
├── Data/
├── Advanced Bayesian Analysis – California Housing Prices.pdf   # Full project report
├── README.md

```

---

## Why This Project Matters

This project demonstrates the ability to:
- Apply **advanced Bayesian modeling** to real-world data
- Handle uncertainty, outliers, and non-standard distributions
- Compare complex probabilistic models rigorously
- Interpret results from both a **statistical and economic** perspective

It reflects a strong interest in **probabilistic modeling, uncertainty quantification, and applied data science**.

---

## Author

**Sika**  
Data Scientist | Bayesian Statistics & Applied Modeling  



---

## Notes

This repository is shared for educational and portfolio purposes.  
Feedback and discussions are welcome.
