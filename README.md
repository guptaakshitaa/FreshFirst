# FreshFirst
# Inventory Risk Prediction using Logistic Regression

This project implements a logistic regression model to identify inventory items at risk of expiration. It is intended for suppliers and warehouse managers handling perishable or time-sensitive goods.

## Objective

To assist in prioritizing which products should be dispatched or consumed first based on estimated shelf life, arrival time, and cost-related factors.

## Features Used

* `sub_category` (label encoded)
* `sale_price`
* Simulated data:

  * `shelf_life_days`: Estimated shelf life in days
  * `arrival_days`: Days since the product arrived
  * `margin_on_arrival`: Remaining life at dispatch time

## Target Variable

* `use_first`:

  * `1` → Item should be prioritized for use or delivery
  * `0` → Item is safe to store for now

## Workflow

1. Load product data (`BigBasket Products.csv`)
2. Label encode `sub_category`
3. Generate synthetic shelf life and arrival data
4. Calculate `margin_on_arrival` as `shelf_life_days - arrival_days`
5. Define the `use_first` label based on remaining shelf life
6. Train a logistic regression model
7. Predict risk scores and classify products
8. Visualize category-wise risk distributions

## Outputs

* A DataFrame including predicted risk classifications and probabilities
* Optional CSV export: `inventory_predictions.csv`
* Visualizations:

  * Risk distribution by category
  * Top products by predicted expiry risk
  * Inventory health summary

## Requirements

* `pandas`
* `numpy`
* `scikit-learn`
* `matplotlib`
* `seaborn`

Install dependencies with:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```

## Future Enhancements

* Replace simulated values with real-time shelf life and logistics data
* Incorporate location-based transit times
* Deploy as a web-based dashboard

## Author

Developed by Akshita Gupta
