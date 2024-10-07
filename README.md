# Pizza Sales Forecasting and Ingredient Planning

## Project Overview

This project aims to forecast pizza sales for the next week and predict the necessary ingredients required to meet that demand. The solution uses historical sales data to build predictive models and ensures that the required ingredients are kept in stock for upcoming orders. 

### Key Objectives:
1. **Sales Forecasting**: Predict pizza sales quantity for the next week.
2. **Ingredient Planning**: Calculate and plan for ingredient purchases based on the forecasted sales to ensure sufficient inventory.
   
## Datasets

### 1. Sales Dataset
The sales dataset contains detailed information about pizza orders, including:
- `pizza_id`: Unique identifier for each pizza.
- `order_id`: Unique identifier for each order.
- `pizza_name_id`: Identifier for the type of pizza.
- `quantity`: Number of pizzas ordered.
- `order_date`: The date the order was placed.
- `order_time`: The time the order was placed.
- `unit_price`: Price per unit of the pizza.
- `total_price`: Total price for the order.
- `pizza_size`: Size of the pizza.
- `pizza_category`: Category (Classic, Gourmet, etc.)
- `pizza_ingredients`: Ingredients used in the pizza.
- `pizza_name`: Name of the pizza.

### 2. Ingredients Dataset
The ingredients dataset includes:
- `pizza_name_id`: Identifier for the pizza.
- `pizza_name`: The name of the pizza.
- `pizza_ingredients`: The ingredients used in each pizza.
- `Items_Qty_In_Grams`: The quantity of each ingredient in grams required per pizza.

## Project Workflow

### 1. **Data Preprocessing**
   - Filter and clean the sales dataset based on pizza name and order date.
   - Perform resampling to aggregate daily sales data.

### 2. **Feature Engineering**
   - Created time-based features such as:
     - `dayofweek`, `dayofmonth`, `dayofyear`, `month`, `year`, `quarter`, `hour`
   - Added lag features (`lag1`, `lag2`, `lag3`) to capture past sales behavior for prediction.

### 3. **Model Training**
   - Applied **XGBoost Regression** to train the sales forecasting model.
   - Performed cross-validation using **TimeSeriesSplit** to avoid data leakage and ensure temporal relevance.
   - Features used: Time-based features and lag variables.

### 4. **Future Prediction**
   - Generated future dates for the next three months to predict future pizza sales.
   - Predicted the total pizza sales for each pizza type over the next three months.

### 5. **Ingredient Planning**
   - Based on predicted sales, calculated the quantity of ingredients needed for each pizza to ensure adequate inventory.

## How to Run the Project

1. **Clone the repository**:
   ```bash
   git@github.com:Aravinth-Megnath/Pizza.git
## Results
  -Forecasted sales for each pizza type for the next three months.
  -Estimated ingredient purchase quantities based on the forecasted sales.
## Libraries Used
  -Pandas: Data manipulation and preprocessing.
  -XGBoost: For regression and forecasting.
  -NumPy: Numerical computations.
  -Scikit-learn: Model validation and splitting.
  -Matplotlib/Seaborn: For visualizing results (if applicable).
## Future Improvements
  -Integrate external data (e.g., holidays, promotions) to improve prediction accuracy.
  -Automate the purchase order process with real-time stock updates.
## Conclusion
This project provides a reliable method for predicting pizza sales and ensuring that the necessary ingredients are stocked in advance. It is designed to help businesses optimize inventory management and reduce costs associated with overstocking or understocking.
