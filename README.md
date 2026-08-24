# quickcart-stockout-risk
Machine learning project for predicting daily SKU-level stockout risk across QuickCart dark stores using inventory, supplier, store, SKU and event data.
# QuickCart Warehouse Inventory Stockout Risk

## Project Overview

This project predicts stockout risk for each SKU at each QuickCart dark store on a daily basis.

The target variable has three classes:

* **Safe** — sufficient stock cover
* **At-Risk** — stock cover is getting close to replenishment time
* **Imminent** — likely to run out before the next supplier delivery

## Dataset

The modeling dataset contains **21,600 store-SKU-day records** covering 12 stores, 60 SKUs and 30 days.

The project combines five tables:

* Store information
* SKU information
* Supplier information
* Event/calendar information
* Daily inventory information

## Data Preparation

The project included:

* Data quality checks
* Missing-value handling
* Table joins using store, SKU, supplier and date keys
* City casing standardization
* Supplier reliability cleaning
* Feature engineering

## Feature Engineering

The main engineered features include:

* Reorder gap
* Days-of-cover ratio
* Recent reorder indicator
* Festival indicator
* Day of month
* Weekend indicator
* Perishable-product indicator

## Machine Learning

Three approaches were compared:

1. Majority-class baseline
2. Logistic Regression
3. Random Forest

A **time-based train/test split** was used. Training data covered October 1–23, while testing data covered October 24–30.

This approach was selected because the same store-SKU combinations appear repeatedly across different days.

## Evaluation

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion matrix

Special attention was given to **Imminent recall**, because failing to identify an actual stockout risk can lead to lost sales.

## Business Insights

The analysis showed several important patterns:

* Festival periods had a substantially higher Imminent stockout rate.
* Lower supplier reliability was associated with higher Imminent risk.
* Perishable products showed higher Imminent risk than non-perishable products.
* Inventory and demand-related variables were among the important predictors in the Random Forest model.

## Tools Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Google Colab

## Project Outcome

The project demonstrates how multi-table operational data can be combined with feature engineering and machine learning to support daily inventory-risk decisions.
