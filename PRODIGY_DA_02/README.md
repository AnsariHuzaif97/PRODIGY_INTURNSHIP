<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=00f2fe&height=200&section=header&text=Task%2002:%20Predictive%20House%20Pricing&fontSize=40&animation=fadeIn&fontAlignY=38&desc=Prodigy%20Infotech%20ML%20Internship&descAlignY=60&descAlign=50" alt="Task 2 Banner" />
</div>

<div align="center">
  <img src="https://img.shields.io/badge/Algorithm-Linear_Regression-013243?style=for-the-badge&logo=scikit-learn" alt="Regression" />
  <img src="https://img.shields.io/badge/Analysis-Statistical_Diagnostics-D00000?style=for-the-badge" alt="Diagnostics" />
  <img src="https://img.shields.io/badge/Python-Data_Science-F7931E?style=for-the-badge&logo=python" alt="Python" />
</div>

<br/>

## 🎯 Project Objective
The goal of this project is to build a robust multivariate **Linear Regression Model** to accurately forecast real estate prices based on 13 distinct property attributes. Beyond simple prediction, this project deeply explores statistical diagnostics, residual analysis, and data transformations to handle real-world price skewness.

---

## ⚙️ Model Pipeline & Preprocessing
The model was trained on `Housing.csv` (545 diverse real estate listings). 
*   **Data Integrity**: `0` Null values.
*   **Categorical Encoding**: Implemented `pd.get_dummies(drop_first=True)` to perfectly one-hot encode binary/categorical variables (e.g., `mainroad`, `guestroom`, `furnishingstatus`) without falling into the dummy variable trap.
*   **Train/Test Split**: 80/20 split using a static random state for reproducible evaluation.

---

## 📈 Model Performance Metrics
The baseline linear regression model achieved the following metrics on the unseen test dataset:

| Metric | Score | Interpretation |
| :--- | :--- | :--- |
| **R-squared ($R^2$)** | `0.65` | The model successfully explains 65% of the variance in housing prices. |
| **RMSE** | `~1.32M` | Average prediction error margin (acceptable given the massive scale of housing prices). |

---

## 🔬 Statistical Diagnostic Analysis

To prove the statistical validity of the linear regression model, a deep dive into residual behavior was conducted:

### 1. Handling Heteroscedasticity via Log Transformation
*   **The Problem**: Initial scatter plots showed increasing variance at higher prices (heteroscedasticity) and severe underprediction of extreme luxury properties.
*   **The Solution**: Applied a **Log Transformation** `log(1 + Price)` to both actual and predicted values.
*   **The Result**: The residuals immediately normalized, variance became uniform across all price ranges, and the model's predictive confidence interval narrowed significantly.

### 2. Residual Distribution & Normality
*   Plotted residual density and confirmed a near-normal Gaussian distribution centered around `0`.
*   Identified that while linearity assumptions hold true, standard linear models naturally struggle with highly skewed luxury outliers.

---

## 💡 Key Feature Insights (Correlation Matrix)

By extracting the regression coefficients and plotting a Seaborn Heatmap, the following business intelligence was derived:

1.  **Primary Driver (`Area`)**: Total square footage has a near `1.0` positive correlation with price. It is the single most predictive feature.
2.  **Structural Drivers**: `Bathrooms`, `Bedrooms`, and `Stories` act as the strongest secondary multipliers to baseline price.
3.  **Negative Drivers**: `Furnishingstatus_unfurnished` holds the strongest negative coefficient, proving that unfurnished houses take a significant, quantifiable hit to market value compared to semi or fully-furnished competitors.

---

## 🛠️ Tools & Libraries Used
*   `scikit-learn`: Implementation of `LinearRegression`, `mean_squared_error`, and `r2_score`.
*   `scipy.stats`: Calculation of skewness and Interquartile Ranges (IQR) for mathematical outlier detection.
*   `seaborn` & `matplotlib`: Regression plotting (`regplot`), residual scatter plots, and correlation heatmaps.

<br>
<div align="center">
  <i>Part of the Prodigy Infotech Internship Portfolio by Md Huzaifa Ansari</i>
</div>
