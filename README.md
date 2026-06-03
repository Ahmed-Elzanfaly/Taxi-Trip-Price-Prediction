# Taxi-Trip-Price-Prediction

## Project Overview

The goal of this project was to build machine learning models capable of predicting taxi trip prices and to understand which factors have the greatest impact on fare estimation.

Rather than focusing only on model performance, I wanted to explore how feature selection affects prediction quality and how different types of information contribute to fare estimation.

---

## Problem Statement

Can we accurately predict the final taxi fare using information available before a trip starts?

To answer this question, I built and compared multiple regression models using different sets of features.

---

## Data Exploration

After exploring the dataset, several observations stood out:

* Trip prices are right-skewed, with most trips costing less than $100.
* Trip distance showed the strongest relationship with trip price.
* Passenger count, weather conditions, and traffic conditions had weaker direct relationships with the target variable.
* The dataset contained missing values across several features, which required preprocessing before model training.

---

## Data Preparation

The following preprocessing steps were applied:

* Removed rows with missing target values.
* Filled numerical missing values using the median.
* Filled categorical missing values using the mode.
* Encoded categorical features using One-Hot Encoding.
* Scaled numerical features using StandardScaler.
* Split the data into training and testing sets.

---

## Experiments

### Experiment 1: Pre-Trip Prediction

The first model was designed to simulate a realistic fare estimation system using only information available before the trip starts:

* Trip Distance
* Passenger Count
* Weather
* Traffic Conditions
* Time of Day
* Day of Week

This experiment achieved reasonable results and showed that trip distance is the dominant factor in predicting fares.

---

### Experiment 2: Adding Pricing Information

In the second experiment, I introduced:

* Base Fare
* Per Kilometer Rate
* Per Minute Rate

Adding these variables improved performance significantly, highlighting the importance of pricing-related information in fare prediction.

---

### Experiment 3: Adding Trip Duration

The final experiment included trip duration as an additional feature.

This version achieved the best overall performance, although trip duration may not always be available before a trip begins in real-world applications.

---

## Models Evaluated

* Linear Regression
* Polynomial Regression
* Ridge Regression
* Lasso Regression

Among all tested models, Polynomial Regression delivered the strongest results.

| Model                 | Test R² |
| --------------------- | ------- |
| Linear Regression     | 0.88    |
| Polynomial Regression | 0.91    |
| Ridge Regression      | 0.88    |
| Lasso Regression      | 0.88    |

---

## Key Takeaways

This project reinforced several important machine learning concepts:

* The quality of features often matters more than the complexity of the model.
* Understanding the business context is essential when selecting features.
* Avoiding data leakage is critical for building realistic predictive models.
* Proper preprocessing can have a significant impact on model performance.

---

## Tools & Libraries

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

---

## Author

Ahmed Elzanfaly

