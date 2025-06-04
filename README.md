# 🏠 Airbnb Nightly Pricing Analysis

This project explores key factors that influence Airbnb nightly pricing using **data mining, statistical analysis, and machine learning models**. The goal is to provide actionable insights for hosts, platform operators, and consumers to understand price drivers and optimize listings.

## 📌 Objectives
- Understand which features most significantly affect Airbnb nightly rates.
- Build interpretable models to predict pricing.
- Perform cluster analysis to segment listings by value and quality.
- Provide data-driven recommendations for pricing strategies.

---

## 📊 Dataset Overview
- **Rows:** 3,982 listings  
- **Columns:** 14 features (mixed numerical and categorical)  
- **Target Variable:** `nightly_rate` (log-transformed due to skewness)  
- No missing values

---

## 🔎 Exploratory Data Analysis (EDA)
- Most listings are **Standard Apartments**, with a balanced season distribution.
- Detected **multicollinearity** between `number_of_bedrooms` and `guest_capacity`, `cleaning_fee`, etc.
- Outliers and skewness in `nightly_rate` led to log transformation.
- Categorical variables were one-hot encoded.

---

## 📈 Modeling Approaches

### 1. Linear Regression
- Applied log transformation on target variable.
- Removed non-significant features to reduce noise.
- Achieved improved model fit with normalized residuals and better R².
- **Key insight:** More bedrooms, peak season, and higher location scores lead to higher prices.

### 2. Decision Tree Regressor
- Captures **nonlinear interactions**.
- Split criteria dominated by `number_of_bedrooms` and `season`.
- Performance similar to linear model, but offers intuitive decision rules.

---

## 🧠 Model Interpretation

- Used **PDP (Partial Dependence Plots)** and **SHAP values** for feature importance and effect direction.
- **Most influential features:**
  - `number_of_bedrooms`
  - `season` (especially peak season)
  - `property_type` (Luxury Homes significantly priced higher)

---

## 🔀 Cluster Analysis (K-Means)
- Clustered listings based on `nightly_rate` and `review_score`
- **Clusters Identified:**
  - `Top-Value`: High reviews, moderate price
  - `Risky Mid-Tier`: Moderate price, low reviews
  - `Budget Friendly`: Low price, decent reviews
  - `Luxury Tier`: High price, high review quality

---

## 📌 Key Takeaways
- Log transformation improves regression model performance.
- Bedrooms and seasonality are **primary drivers** of pricing.
- Hosts can adjust pricing and positioning based on cluster insights.
- Decision tree models offer transparent, rule-based segmentation.

---

## 🛠 Tools & Libraries
- Python (Pandas, NumPy, Scikit-learn, Statsmodels)
- Matplotlib, Seaborn
- SHAP, PDPbox
- Jupyter Notebook
