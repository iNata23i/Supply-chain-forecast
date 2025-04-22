# Supply Chain Forecasting for a Beverage Manufacturing Company
## Project Overview
This project focuses on forecasting delivery lead times within the supply chain of a beverage manufacturing company. By analyzing historical sales data, we aim to predict the time between order placement and delivery, enhancing operational efficiency and customer satisfaction.

## Objectives
Predict Delivery Lead Time: Estimate the number of days between order date and delivery date.

Identify Key Factors: Determine which variables most significantly impact delivery times.

Provide Interactive Tool: Develop a user-friendly interface for stakeholders to obtain lead time predictions.

## Dataset
The dataset comprises sales orders with the following relevant fields:

OrderDate: Date when the order was placed.

DeliveryDate: Date when the order was delivered.

WarehouseCode: Identifier for the warehouse processing the order.

_ProductID: Identifier for the product ordered.

Order Quantity: Number of units ordered.

## Data Preprocessing
Lead Time Calculation: Computed as the difference in days between DeliveryDate and OrderDate.

Data Cleaning: Removed entries with missing or negative lead times.

Feature Selection: Chose WarehouseCode, _ProductID, and Order Quantity as predictors.

Encoding: Applied one-hot encoding to categorical variables.

## Model Training
Utilized a Random Forest Regressor to model the relationship between the selected features and the delivery lead time.

from sklearn.ensemble import RandomForestRegressor
model = RandomForestRegressor(random_state=42)
model.fit(X_train, y_train)

## Interactive Demo with Gradio
To enhance accessibility, an interactive web interface was developed using Gradio. This allows users to input order details and receive immediate lead time predictions.

Features:
Warehouse Selection: Dropdown menu to choose the warehouse.

Product Selection: Dropdown menu to select the product.

Order Quantity: Slider to specify the number of units.

Usage:

import gradio as gr

gr.Interface(
    fn=predict_lead_time,
    inputs=[
        gr.Dropdown(warehouses, label="Select Warehouse"),
        gr.Dropdown(products, label="Select Product"),
        gr.Slider(1, 100, step=1, label="Order Quantity")
    ],
    outputs="text",
    title="Order Lead Time Forecaster"
).launch(share=True)
Output:
Displays the estimated delivery lead time in days based on the input parameters.

## Feature Importance
Analyzed the impact of each feature on the prediction to understand their significance.

import matplotlib.pyplot as plt

coeffs = pd.Series(model.feature_importances_, index=X_train.columns).sort_values()
coeffs.plot(kind='barh', figsize=(10, 6), title='Feature Importance on Lead Time')
plt.tight_layout()
plt.show()

## Business Value
Customer Insights: Identify customers contributing the most to revenue.

Sales Team Performance: Evaluate which teams are securing significant deals.

Strategic Planning: Inform decisions on bonuses, retention strategies, and resource allocation.

## Conclusion
This project demonstrates the application of machine learning techniques to predict delivery lead times, providing valuable insights for supply chain optimization in the beverage manufacturing industry.

