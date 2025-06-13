
# 🏠 Housing Price Prediction using Linear Regression

This project is part of my **internship at Oasis Infobyte**, where I built a regression model to predict housing prices using key property features. It includes full-cycle data science processes—exploratory data analysis (EDA), feature engineering, model training, and performance evaluation.

---

##  Project Objectives

- Perform exploratory data analysis (EDA)
- Clean and preprocess the housing dataset
- Handle outliers using IQR-based capping
- Convert categorical variables into numerical format (binary)
- Select relevant features based on correlation
- Train and evaluate a Linear Regression model
- Visualize results including correlation heatmap and actual vs predicted values

---

##  Dataset Summary

| Feature              | Description                          |
|----------------------|--------------------------------------|
| `price`              | Target variable (house price)        |
| `area`               | Total area of the property           |
| `bedrooms`           | Number of bedrooms                   |
| `bathrooms`          | Number of bathrooms                  |
| `stories`            | Number of floors                     |
| `parking`            | Number of parking spots              |
| `mainroad`, `guestroom`, `basement`, `hotwaterheating`, `airconditioning`, `prefarea` | Binary categorical |
| `furnishingstatus`   | Furnishing type (furnished/unfurnished) |

---

## Data Preprocessing & Feature Engineering

- Capped extreme values in the `price` column using the Interquartile Range (IQR) method
- Converted all categorical variables to binary using `pd.get_dummies()`
- Selected features using correlation with the target
- Scaled features using `StandardScaler`

---

## 📈 Visualizations

### 🔥 Correlation Heatmap

Shows the strength and direction of linear relationships between variables.

```python
import seaborn as sns
import matplotlib.pyplot as plt

plt.figure(figsize=(12,8))
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.title('Feature Correlation Heatmap')
plt.show()
```

### Actual vs Predicted Prices

plt.scatter(y_test, predictions, alpha=0.7, color='teal')
plt.xlabel("Actual Price")
plt.ylabel("Predicted Price")
plt.title("Actual vs Predicted Prices")
plt.grid(True)
plt.show()

---

## ✅ Model Evaluation


