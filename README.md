# Retail Price Optimization
This repository contains a project focused on predicting future retail prices using historical sales and competitor data. The project includes comprehensive data preprocessing, Exploratory Data Analysis (EDA), feature engineering, and the implementation of multiple regression models. The XGBoost Regressor, which demonstrated the highest accuracy, was selected and tuned for deployment.

# Project Workflow
1. Data Preparation: Aggregated monthly product-level data, converted date columns and engineered temporal features, and winsorized outliers at 5th and 95th percentiles.
2. Exploratory Data Analysis (EDA): Identify patterns and relationships in the dataset.
3. Feature Engineering and Scaling: Created price difference and percentage difference features for competitors, and scaled numerical features (excluding identifiers and target).
4. Model Training: Trained eights regression models (i.e., Random Forest, Ridge Regression, Linear Regression, Decision Tree, Gradient Boosting, XGBoost, Support Vector Regressor, and K-Nearest Neighbors).
5. Model Evaluation: Compare model performance metrics.
6. Hyperparameter Tuning: Used GridSearchCV to optimize XGBoost parameters.
7. Model Explainability: Permutation Importance identified 'unit_price' as the most influential feature, and SHAP values provided insights into individual predictions.

# Dataset Description
The dataset includes monthly sales and pricing data for retail products, competitor pricing, freight costs, product scores, and temporal indicators. Key features include:
1. unit_price: Product’s own price
2. qty: Quantity sold
3. total_price: Revenue
4. freight_price: Delivery cost
5. comp1_price, comp2_price, comp3_price: Competitor prices
6. product_score, comp_score: Quality indicators
7. holiday, weekend: Temporal flags
8. lag_price: Target variable (next month’s price)

# Visualizations
The EDA phase involves:
1. Line plots for price and quantity trends.
2. Scatter plots for price vs. quantity.
3. Histograms and box plots for distribution analysis.
4. Competitor comparisons over time.
5. Feature importance and SHAP summary plots.
6. Actual vs. predicted price scatter plot.

# Model Selection
The XGBoost Regressor was selected based on its superior performance metrics (i.e., final performance on test set gave RMSE of 7.93, R² Score of 0.99, and MAE of 4.43). A separate script, model_selection.ipynb, can be used to compare models and select the best one based on RMSE and R² Score. If Gradient Boosting performs comparably, XGBoost is still preferred due to its explainability and tuning flexibility.
