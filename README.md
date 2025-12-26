

# 🪙 Gold Price Prediction (2013–2023) — Machine Learning Regression Project

This project builds a machine-learning regression model to predict gold prices using historical financial market data from 2013 to 2023. The workflow includes data cleaning, feature engineering, preprocessing, model comparison, hyperparameter tuning, and an interactive price-prediction system.

---

## 📂 Dataset & Features

The dataset contains historical gold trading records with fields such as:

* Price (target variable)
* Open price
* High price
* Low price
* Volume
* Date

After preprocessing, the final feature set used for modeling:

* Open
* High
* Low
* Vol.
* Date (Seconds)

Target variable:

* **Price (₹)**

---

## 🧹 Data Cleaning & Feature Engineering

* Dropped missing records
* Removed `Change %` column
* Converted price values from `string → numeric`
* Converted volume notation:

  * `100K → 100000`
  * `2.5M → 2500000`
* Converted dates to UNIX timestamp (seconds)
* Performed train–test split
* Scaled features using `StandardScaler`

---

## 🧪 Model Training & Cross-Validation

Evaluated multiple regression algorithms using 5-fold CV:

| Model             | R² Score   |
| ----------------- | ---------- |
| Linear Regression | **99.61%** |
| Decision Tree     | 95.64%     |
| Random Forest     | 96.45%     |
| KNN               | −115.07%   |
| AdaBoost          | 90.24%     |
| Gradient Boosting | 96.00%     |
| XGBoost           | 95.00%     |
| SVM               | −1250.06%  |

**Shortlisted top models**

* Random Forest
* Gradient Boosting
* XGBoost
* AdaBoost

---

## 🔧 Hyperparameter Tuning (GridSearchCV)

### Random Forest

```
max_depth = 11
max_features = 4
CV Score = 0.9991
```

### Gradient Boosting

```
learning_rate = 0.18
max_depth = 5
CV Score = 0.9991
```

### XGBoost

```
colsample_bytree = 1.0
gamma = 2
CV Score = 0.9990
```

Most tuned models achieved scores close to **perfect fit** on this dataset.

---

## 🏁 Final Model Selection

Final chosen model: **AdaBoost Regressor**

Reason for selection:

* strong performance
* lower risk of overfitting
* smoother behavior on unseen inputs

The model was trained on scaled features and evaluated on test data.

---

## 💻 Interactive Prediction System

User enters:

* Open price
* High price
* Low price
* Volume
* Date (YYYY-MM-DD)

Steps:

1. Date is converted to UNIX timestamp
2. Features are scaled
3. Model predicts price

Output:

👉 **Predicted Gold Price (₹)**

---

## 🛠️ Tech Stack

* Python • NumPy • Pandas
* Scikit-Learn
* XGBoost
* Matplotlib • Seaborn

---

## 🚀 Future Improvements

* Use time-series-aware validation (walk-forward CV)
* Add lag features & rolling statistics
* Experiment with LSTM / Prophet
* Deploy via Streamlit or Flask


