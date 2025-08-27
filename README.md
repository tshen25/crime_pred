# Crime Prediction Project

This project explores linear regression modeling to predict crime rates in U.S. cities using data from [Statsci.org](http://www.statsci.org/data/general/uscrime.txt).

---

## 🔍 Objective
Predict the observed crime rate in a city based on socioeconomic and demographic factors such as education, inequality, and probability of conviction.

---

## 📊 Methods

### Naive Model (all predictors)
- Built an initial linear regression model using all available predictors.  
- Found signs of overfitting: prediction fell outside the range of observed crime rates.  

### Reduced Model (significant predictors only)
- Selected predictors with p-values < 0.05 (`M`, `Ed`, `Ineq`, `Prob`).  
- Prediction improved but explained variance dropped (**Adjusted R² = 0.19**).  

### Recursive Feature Elimination (RFE)
- Applied RFE with cross-validation to identify the best subset of predictors.  
- Optimal model selected **10 predictors**: `U1`, `Prob`, `LF`, `Po1`, `Ed`, `U2`, `Po2`, `M`, `Ineq`, `So`.  
- Achieved better performance (**RMSE = 230.9, R² = 0.66**).  

---

## 📈 Results
- **Naive model prediction**: ~155.4 (unrealistic)  
- **Reduced model prediction**: ~897.2  
- **Best model (RFE, 10 predictors)**: ~870.7  

The best model balances interpretability and accuracy, producing a realistic prediction within the observed crime range.  

---

## ⚙️ Tools & Packages
- **R packages**: `tidyverse`, `caret`, `ggplot2`  
- **Techniques**: Linear Regression, Feature Selection (RFE), Cross-Validation  
