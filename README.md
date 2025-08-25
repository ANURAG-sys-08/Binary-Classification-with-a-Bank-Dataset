Kaggle Playground Series: Bank Term Deposit Prediction

📋 Overview

This repository contains the complete code and methodology for the Kaggle Playground Series competition focused on predicting whether a client will subscribe to a bank term deposit. The project demonstrates an end-to-end machine learning workflow, from initial data exploration and preprocessing to advanced model tuning and final submission.

The primary goal was to build a high-performance binary classification model, evaluated on the ROC AUC metric.

Final Public Leaderboard Score: 0.96856

🚀 Project Workflow & Methodology

The project followed a structured and iterative approach to maximize model performance.

1. Exploratory Data Analysis (EDA)

Initial Analysis: The dataset was thoroughly investigated to understand the distributions of numerical and categorical features.

Target Variable Imbalance: A significant class imbalance was identified in the target variable (y), which heavily influenced the choice of evaluation metrics and modeling techniques.

Visualizations: A variety of plots were used to uncover relationships between features and the target variable.

2. Data Preprocessing & Feature Engineering

A robust preprocessing pipeline was established to prepare the data for modeling.

Categorical Data: Features like job, education, and poutcome were converted into a numerical format using one-hot encoding.

Binary Features: Simple 'yes'/'no' columns were mapped to 1/0.

Feature Creation: A new feature, pcontacted, was engineered from the pdays column to explicitly capture whether a client had been contacted in a previous campaign.

3. Modeling & Hyperparameter Tuning

Model Selection: Several models were trained and evaluated, including Logistic Regression, XGBoost, and LightGBM. The gradient boosting models proved to be the most effective.

Tuning Strategy: A sophisticated "coarse-to-fine" hyperparameter tuning strategy was implemented:

Randomized Search (RandomizedSearchCV): A broad search was conducted to efficiently explore the hyperparameter space and identify the most promising regions.

Grid Search (GridSearchCV): A focused grid search was then performed on a smaller, more refined range of parameters to pinpoint the optimal settings.

Evaluation Metric: The entire tuning process was optimized for the official competition metric, ROC AUC, by setting scoring='roc_auc'.

4. Final Model & Ensembling

The final, tuned LightGBM model was selected as the top performer.

An ensemble model, created by averaging the predictions of the tuned LightGBM and XGBoost models, was also created and submitted to test for performance improvements.

📊 Results & Visualizations

The final tuned LightGBM model achieved a public leaderboard score of 0.96856. This marked a significant improvement of nearly 10 percentage points over the initial baseline models, highlighting the critical impact of a rigorous tuning process.

This repository's notebook includes a comprehensive suite of visualizations:

Model Performance Comparison: Bar charts comparing the ROC AUC scores of all models at different stages (baseline, randomized search, grid search).

ROC Curves: A visual comparison of the ROC curves for the final tuned models.

Feature Importance: Plots showing the most influential features for the best-performing model.

Note: While the sole goal of the competition was to maximize the submission score, this notebook was developed as a portfolio piece. Therefore, it includes extensive visualizations and evaluation metrics beyond what was strictly necessary, in order to provide a clear and comprehensive demonstration of the project's methodology and results.

🛠️ Tools & Libraries

Data Manipulation: Pandas, NumPy

Machine Learning: Scikit-Learn, XGBoost, LightGBM

Visualization: Matplotlib, Seaborn
