# Supply Chain Forecasting for a Beverage Manufacturing Company
## Project Overview
This project focuses on forecasting delivery lead times within the supply chain of a beverage manufacturing company. By analyzing historical sales data, we aim to predict the time between order placement and delivery, enhancing operational efficiency and customer satisfaction.

## Objectives
- Predict Delivery Lead Time: Estimate the number of days between order date and delivery date.
- Identify Key Factors: Determine which variables most significantly impact delivery times.
- Provide Interactive Tool: Develop a user-friendly interface for stakeholders to obtain lead time predictions.

## Dataset
The dataset comprises sales orders with the following relevant fields:

- _OrderDate_: Date when the order was placed.
- _DeliveryDate_: Date when the order was delivered.
- _WarehouseCode_: Identifier for the warehouse processing the order.
- __ProductID_: Identifier for the product ordered.
- _OrderQuantity_: Number of units ordered.

## Data Preprocessing
- Lead Time Calculation: Computed as the difference in days between _DeliveryDate_ and _OrderDate_.
- Data Cleaning: Removed entries with missing or negative lead times.
- Feature Selection: Chose _WarehouseCode_, __ProductID_, and _OrderQuantity_ as predictors.
- Encoding: Applied one-hot encoding to categorical variables.

## Model Training
The forecasting models in this project are based on classical time series methods:

- ARIMA
  
Used to forecast monthly order quantity for a selected warehouse based on historical data. The ARIMA(1,1,1) model was fitted to the time series after resampling daily sales to monthly totals.
-  SARIMAX
  
Used to forecast monthly revenue for a specific sales channel (e.g., "Online"). This model accounts for both trend and seasonality (with seasonal order (1, 1, 1, 12)).

These models were chosen for their interpretability and effectiveness on relatively small time series datasets.

## Interactive Demo with Gradio
To enhance accessibility, an interactive web interface was developed using Gradio. This allows users to input order details and receive immediate lead time predictions.

Features:
- Warehouse Selection: Dropdown menu to choose the warehouse.
- Product Selection: Dropdown menu to select the product.
- Order Quantity: Slider to specify the number of units.
  
Output:
Displays the estimated delivery lead time in days based on the input parameters.

## Feature Importance
Analyzed the impact of each feature on the prediction to understand their significance.

## Business Value

- Customer Insights: Identify customers contributing the most to revenue.
- Sales Team Performance: Evaluate which teams are securing significant deals.
- Strategic Planning: Inform decisions on bonuses, retention strategies, and resource allocation.

## Conclusion
This project demonstrates the application of machine learning techniques to predict delivery lead times, providing valuable insights for supply chain optimization in the beverage manufacturing industry.

