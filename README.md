# DVD Rental Duration Prediction

## Project Overview
This project is a solution to a DataCamp challenge on regression models. The goal of the project is to build a regression model that predicts how many days a customer will rent a DVD for, based on various features provided in the dataset. The objective is to recommend a model with a mean squared error (MSE) of less than 3 on the test set.

## Goal
- **Objective**: Recommend a model yielding a mean squared error (MSE) less than 3 on the test set.
- **Deliverables**: 
  - The recommended model saved as a variable named `best_model`.
  - The MSE of the recommended model saved as `best_mse`.

## Background
A DVD rental company is looking for a way to predict the number of rental days for each customer to improve inventory planning and overall efficiency. They have provided a dataset containing various features about the rentals, and the task is to apply regression models to make predictions about the rental duration.

## Dataset
The dataset provided by the company is `rental_info.csv` and includes the following features:

- **rental_date**: The date and time the customer rents the DVD.
- **return_date**: The date and time the customer returns the DVD.
- **amount**: The amount paid by the customer for renting the DVD.
- **amount_2**: The square of the amount.
- **rental_rate**: The rate at which the DVD is rented.
- **rental_rate_2**: The square of the rental rate.
- **release_year**: The year the movie being rented was released.
- **length**: The length of the movie in minutes.
- **length_2**: The square of the length.
- **replacement_cost**: The cost to the company to replace the DVD.
- **special_features**: Any special features on the DVD, such as trailers or deleted scenes.
- **NC-17**, **PG**, **PG-13**, **R**: Dummy variables representing the movie's rating. These take a value of 1 if the movie is rated accordingly and 0 otherwise.

## Project Workflow
The key steps taken in the project are outlined below:

1. **Calculating the Number of Rental Days**: 
   - The target variable, rental duration, is computed as the difference between `return_date` and `rental_date`.

2. **Adding Dummy Variables**: 
   - Dummy variables were created based on the `special_features` column to represent the presence of each feature (e.g., deleted scenes, trailers).

3. **Train-Test Split**: 
   - The dataset was split into training and testing sets to evaluate the model’s performance.

4. **Feature Selection**: 
   - A Lasso regression model was used to perform feature selection. Features with coefficients greater than 0 were selected for use in the final model.

5. **Model Selection and Hyperparameter Tuning**: 
   - 3 regression models were tested: (LinearRegression, DecisionTreeRegressor, RandomForestRegressor) and hyperparameter tuning was performed to optimize performance.

6. **Predictions on the Test Set**: 
   - The selected models were used to predict the rental duration on the test set.

7. **Evaluation with Mean Squared Error (MSE)**: 
   - The MSE was calculated to evaluate the model's performance. The goal was to achieve an MSE of less than 3 on the test set.

## Results
The model that performed best was saved as a variable `best_model` and achieved a MSE on the test set of less than 3, saved as `best_mse`.
