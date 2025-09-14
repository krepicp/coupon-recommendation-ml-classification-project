# Will the Driver Accept the Coupon?  
## ***Coupon Acceptance Prediction: ML Classification Project***

---

## 📌 1. Short Introduction & Business Context

Coupons are a widely used marketing tool to attract new customers, build loyalty, and boost sales.  

Since customer preferences differ, the key challenge is to recommend the **right coupon** to the **right person** at the **right time**.  

This project explores **coupon acceptance prediction** using ML classification models. It analyzes which factors influence acceptance and provides business recommendations for smarter coupon strategies.

---

## 🎯 2. Project Goals

- **Technical goal** → Build and compare different ML classification models for coupon acceptance prediction.
  
- **Business goal** → Improve coupon redemption rates by identifying people most likely to accept coupons.  

---

## 📊 3. Dataset

To conduct the analysis, the dataset **"In-Vehicle Coupon Recommendation"** from the UC Machine Learning Repository was used. The data was collected via Amazon Mechanical Turk survey.

**Source:** [Dataset](https://archive.ics.uci.edu/dataset/603/in+vehicle+coupon+recommendation) 

The dataset contains **12 684 observations**, **25 features**, and target variable **Y** (Y=1 - coupon accepted; Y=0 - coupon rejected)

Features describe **driving scenarios** (e.g., time, weather conditions, passengers, destination) and **driver attributes** (e.g., age, income, education, marital status)

---

## ⚙️ 4. Data Preprocessing & EDA

The source data was adapted to the needs of the analysis. 

**Key data transformation steps include:**

- Removal of irrelevant/redundant features and rows with missing values.  
- Creation of new aggregated variables.
- Simplification of original variables.  
- Dropping highly correlated variables.
- Data type adjustment.

**Exploratory Analysis** revealed the first patterns in coupon acceptance behaviour and allowed for a preliminary assessment of the 'perfect driver-consumer' profile.

The **ready-for-modeling** dataset had **12 079 observations** and **17 features**.

---

## 🤖 5. Modeling & Evaluation

In total, **six models** were trained and tuned:  
- Logistic Regression  
- Decision Tree  
- Random Forest  
- Gradient Boosting  
- XGBoost  
- CatBoost  

**RandomizedSearchCV** was used for hyperparameter tuning. 

Models were evaluated using three metrics: **F1-Score, Accuracy, ROC-AUC**.  
For each model, the ROC Curve and Confusion Matrix were added.

---

## 📈 6. Model Comparison

The table below briefly summarizes the results of the obtained models:

| Model              | Accuracy | F1-Score | ROC-AUC |
|--------------------|----------|----------|---------|
| Logistic Regression| 0.707506 | 0.759310 | 0.757185|
| Decision Tree      | 0.694812 | 0.762559 | 0.742136|
| Random Forest      | 0.720751 | 0.767142 | 0.782917|
| Gradient Boosting  | 0.719371 | 0.775348 | 0.783245|
| XGBoost            | 0.727925 | 0.772076 | 0.794163|
| **CatBoost**       | **0.732892** | **0.776133** | **0.799887** |



- All models achieved at least **0.70** across most metrics (except Decision Tree on Accuracy).  
- **CatBoost** performed best overall, showing the strongest predictive ability.

---

## 🔍 7. Insights & Interpretation
- **CatBoost feature importance** identified the strongest predictors of coupon acceptance.

- **Logistic Regression coefficients** allowed interpretation of direction and effect strength.  

**Examples of positive drivers of acceptance:**  
- Frequent visits to coupon locations  
- Traveling with friends/partner  
- Sunny weather  
- Younger age (under 30)
- Physical or Technical & Engineering jobs

**Examples of negative drivers of acceptance:**  
- Early morning or late evening hours  
- Long distance to the location
- Rainy or snowy day
- Older age (50+) or being retired
- High education level 

---

## ✅ 8. Conclusions & Business Recommendations
ML models can effectively predict coupon acceptance and support personalized coupon strategies.  

Recommendations:  
1. **Target the right audience** → Younger drivers, traveling with friends/partner, frequent visitors.  
2. **Offer what works best** → Carry-Out & Take-Away coupons show the highest acceptance rates.  
3. **Leverage timing & context** → Avoid early mornings/late evenings; *Sunny afternoon? Perfect time for coffee!*  
4. **Keep it close** → Coupons for nearby locations are more likely to be accepted.  
5. **Explore alternatives** → Test non-coupon strategies for harder-to-reach groups (older drivers, those far from coupon locations).  

---

## 📂 9. Project Structure

/notebooks/
├── data_preprocessing_and_EDA.ipynb
├── modeling_and_evaluation.ipynb
/presentation/
└── presentation.pdf # Extended project summary & results
README.md # Project description

---

## 🛠️ 10. Technologies & Libraries
- Python  
- Numpy, Pandas  
- Matplotlib, Seaborn  
- Scikit-learn  
- XGBoost, CatBoost  

---


