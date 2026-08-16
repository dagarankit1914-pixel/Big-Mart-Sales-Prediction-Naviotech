# Big Mart Sales Prediction Using Machine Learning

## Project Overview

This project focuses on predicting product sales across different Big Mart outlets using machine learning.

The project follows a complete machine-learning workflow, starting with understanding and preparing the dataset and ending with training and evaluating a regression model. The main goal is to predict `Item_Outlet_Sales` using product and outlet-related information.

An XGBoost Regressor is used as the final machine-learning model.

## Project Objectives

The main objectives of this project are to:

- Understand the structure of the Big Mart sales dataset.
- Identify and handle missing values.
- Clean inconsistent categorical values.
- Explore numerical and categorical features.
- Convert categorical features into numerical representations.
- Split the dataset into training and testing sets.
- Train an XGBoost regression model.
- Evaluate the model using the R² score.
- Understand how well the model performs on unseen data.

## Dataset

The project uses the Big Mart sales training dataset (`Train.csv`).

The dataset contains product-level and outlet-level information. The target variable is `Item_Outlet_Sales`.

Important features include:

- `Item_Identifier`
- `Item_Weight`
- `Item_Fat_Content`
- `Item_Visibility`
- `Item_Type`
- `Item_MRP`
- `Outlet_Identifier`
- `Outlet_Establishment_Year`
- `Outlet_Size`
- `Outlet_Location_Type`
- `Outlet_Type`

## Project Workflow

1. Import the required Python libraries.
2. Load and inspect the dataset.
3. Examine the dataset structure and feature types.
4. Identify missing values.
5. Handle missing `Item_Weight` and `Outlet_Size` values.
6. Explore numerical and categorical features through visualizations.
7. Standardize inconsistent `Item_Fat_Content` values.
8. Encode categorical features using `LabelEncoder`.
9. Separate the input features from the target variable.
10. Split the data into training and testing sets using an 80:20 split.
11. Train an XGBoost Regressor.
12. Evaluate the model using the R² score.

## Data Preprocessing

Missing values are handled before model training.

For `Item_Weight`, missing values are filled using the mean of the available values.

For `Outlet_Size`, missing values are handled using the most common outlet size associated with the relevant outlet type.

The `Item_Fat_Content` feature contains different labels representing the same categories. These are standardized so that `LF` and `low fat` become `Low Fat`, while `reg` becomes `Regular`.

Categorical features are then converted into numerical values using `LabelEncoder`.

## Exploratory Data Analysis

The notebook explores the distribution of numerical features including `Item_Weight`, `Item_Visibility`, `Item_MRP`, `Outlet_Establishment_Year`, and `Item_Outlet_Sales`.

Categorical features are also examined to understand the distribution of products and outlets in the dataset.

## Machine Learning Model

### XGBoost Regressor

The final model is an XGBoost Regressor. XGBoost is a gradient-boosting algorithm based on decision trees and is used here as a regression model because `Item_Outlet_Sales` is a continuous numerical target.

The dataset is divided into 80% training data and 20% testing data. A fixed random state is used so that the train-test split is reproducible.

## Model Performance

The model is evaluated using the R² (R-squared) score.

| Evaluation Set | R² Score |
|---|---:|
| Training Data | **87.51%** |
| Testing Data | **51.56%** |

The model performs substantially better on the training data than on the unseen testing data. This indicates a noticeable train-test performance gap and suggests some degree of overfitting.

The testing score still shows that the model captures a meaningful portion of the variation in Big Mart sales.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- Google Colab / Jupyter Notebook

## Project Structure

```text
Big_Mart_Sales_Prediction_Naviotech/
├── Big_Mart_Sales_Prediction_Naviotech_Final.ipynb
├── README.md
└── Train.csv
```

## How to Run the Project

1. Open the `.ipynb` notebook in Google Colab or Jupyter Notebook.
2. Make sure `Train.csv` is available in the expected location.
3. Run the notebook from the beginning.
4. If using Google Colab and the dataset is not already available in `/content/`, upload `Train.csv` when prompted.
5. Run all cells to reproduce the data analysis, preprocessing, model training, and evaluation.

## Conclusion

This project demonstrates an end-to-end machine-learning workflow for predicting Big Mart outlet sales.

The project covers real-world data preparation, missing-value treatment, categorical data cleaning, exploratory analysis, feature encoding, model training, and evaluation.

The XGBoost model achieved an R² score of **87.51% on the training data** and **51.56% on the testing data**. The difference between these scores highlights some overfitting and also shows why evaluation on unseen data is important.

Overall, the project provides practical experience with preparing a real-world dataset and applying a regression algorithm to a sales-prediction problem.
