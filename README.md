# 🌍 Life Expectancy Prediction using Machine Learning

## 📌 Overview
This project predicts **life expectancy** using real-world health, economic, and demographic data from the WHO dataset.

Unlike typical ML projects, this work focuses on:
- Thoughtful preprocessing decisions
- Avoiding data leakage
- Model generalization
- Model interpretability using SHAP

---

## 🎯 Problem Statement
Predict **life expectancy** of a country based on:
- Health indicators (HIV/AIDS, mortality, BMI, vaccinations)
- Economic indicators (GDP, income composition, expenditure)
- Demographic indicators (population, thinness)

---

## 📊 Dataset
- **Source:** WHO Life Expectancy Dataset  
- **Target Variable:** `Life expectancy`

### Feature Categories:
- 🏥 Health: Adult mortality, HIV/AIDS, immunization
- 💰 Economic: GDP, income composition, expenditure
- 👥 Demographic: Population, thinness

### Challenges:
- Missing values
- Skewed distributions
- Real-world noise
- Non-linear relationships

---

## ⚙️ Project Workflow

### 1️⃣ Exploratory Data Analysis
- Identified missing values and outliers
- Observed strong **non-linear relationships**
- Detected skewed and heavy-tailed features

---

### 2️⃣ Outlier Handling
- Applied **selective IQR-based capping (winsorization)**
- Avoided modifying meaningful extreme values (GDP, population)
- Focused only on measurement-based features

---

### 3️⃣ Missing Value Imputation
- Used **median-based imputation**
- Applied **country-aware interpolation**
- Avoided global mean → reduced bias

---

### 4️⃣ Feature Engineering
- Evaluated impact of `Country` feature
- Used encoding carefully to avoid **data leakage**
- Compared models with and without country feature

---

### 5️⃣ Model Building
Models implemented:
- Linear Regression
- KNN Regressor
- Support Vector Regressor (SVR)
- Decision Tree Regressor

---

### 6️⃣ Hyperparameter Tuning
- Used **GridSearchCV**
- Cross-validation applied
- Optimized for **Mean Squared Error**

---

## 📈 Results

| Model | Performance |
|------|------------|
| Linear Regression | ❌ Underperformed |
| KNN | ⭐ Best |
| SVR | ✅ Strong |
| Decision Tree | ✅ Strong |

### Key Observations:
- Data is **highly non-linear**
- Linear models fail to capture complexity
- Non-linear models significantly outperform

---

## 🔍 Model Explainability (SHAP)

To make the model interpretable, **SHAP (SHapley Additive Explanations)** was applied.

### Key Insights:
- 🔴 **HIV/AIDS** → Strong negative impact on life expectancy
- 🟢 **Income composition** → Strong positive impact
- 🔴 **Adult Mortality** → Major negative factor
- 🟢 **Schooling** → Positive influence

### Visualizations:
- SHAP Summary Plot (global importance)
- SHAP Bar Plot (mean impact)
- SHAP Force Plot (individual prediction explanation)

---

## 🧠 Key Learnings

- Real-world ML requires **selective preprocessing**
- Some features (like Country) can act as **shortcuts**
- High accuracy ≠ good model (generalization matters)
- **Interpretability (XAI)** is crucial in real-world systems
- Data understanding > model complexity

---

## 🚀 Future Improvements

- Add ensemble models (Random Forest, XGBoost)
- Perform region-based error analysis
- Detect bias across countries/income groups
- Deploy as a web app (Streamlit)
- Extend to research-level explainability study

---

## 🛠️ Tech Stack

- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn
- SHAP (Explainable AI)

---

## 📌 Conclusion

This project demonstrates how combining:
- Strong preprocessing
- Proper model selection
- Explainability (SHAP)

can lead to **robust and interpretable machine learning systems**.