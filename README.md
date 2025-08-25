
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
Visualizing how well the model performed in predicting price values suing scatter plot

```python
plt.scatter(y_test, predictions, alpha=0.7, color='teal')
plt.xlabel("Actual Price")
plt.ylabel("Predicted Price")
plt.title("Actual vs Predicted Prices")
plt.grid(True)
plt.show()
```

---

## ✅ Model Evaluation
Evaluated using the following metrics:
Mean Squared Error (MSE)
Root Mean Squared Error (RMSE)
R-squared Score (R²)

Test Set Performance (Capped Price):

Training Performance:
MSE: 209062074566.50, RMSE: 457233.06, R²: 0.9322

Test Performance:
MSE: 2275535313863.77, RMSE: 1508487.76, R²: 0.5498

---

## Tools Used
- Python:core programming language
- Pandas: For data loading, manipulation, and cleaning.
- NumPy: For numerical computations and handling arrays.
- Matplotlib: Used for creating basic plots.
- Seaborn: For enhanced visualizations, including heatmaps and histograms.
- Scikit-learn:Linear Regression modeling and evaluation
= Google Colab: Used as the coding environment:

---

 ## Key Insights
- Area, bedrooms, bathrooms, and air conditioning showed strong positive correlation with house price.
- Furnishing status (e.g., unfurnished) showed negative correlation, suggesting it affects value perception.
- Removing extreme outliers helped stabilize model performance and improved generalization on new data.
- Although linear regression worked reasonably well, there’s room to explore advanced models for improved accuracy (e.g., Random Forest or Gradient Boosting).
- Visualizations such as correlation heatmaps and scatter plots provided clear insight into relationships and model behavior.

In summary, this project demonstrates how linear regression can effectively predict house prices based on key property features such as area, bathrooms, and furnishing status.
