# Shipping Charge Prediction

## Project Overview

This project aims to analyze and predict shipping charges based on various features such as geographical coordinates, distances, weights, and other relevant attributes. The dataset used in this project consists of shipping details, including shipper and receiver addresses, weights, invoice amounts, and other charges.

## Data Description

- `Charge_Detail.csv`: Raw dataset containing shipping details.
- `Shipper_lat_long_df.csv`: Geocoded shipper addresses with latitude and longitude.
- `Receiver_lat_long_df.csv`: Geocoded receiver addresses with latitude and longitude.
- `cleaned_lat_long_charge_detail.csv`: Cleaned dataset with latitude and longitude information.
- `Final_DataSet.csv`: Final dataset used for model training and evaluation.

## Data Preprocessing

Data preprocessing includes:
- Adjusting pandas settings to display all columns.
- Reading the CSV file into a DataFrame.
- Cleaning and transforming data by filling missing values and creating new columns.
- Standardizing postal codes and creating full address columns for both shippers and receivers.

## Geocoding

Geocoding is performed using an API to get latitude and longitude based on postal codes and countries. Results are saved in separate CSV files (`Shipper_lat_long_df.csv` and `Receiver_lat_long_df.csv`).

## Distance Calculation

Distance between shipper and receiver addresses is calculated using the `geopy` library. A new column `Distance` is added to the dataset to store these values.

## Machine Learning Model

- **Features**: Latitude and longitude of shipper and receiver, distance, and actual weight.
- **Target**: Net charge.
- **Model**: RandomForestRegressor with hyperparameter tuning using GridSearchCV.
- Data is split into training and testing sets, and standardized using StandardScaler.

## Evaluation

- Cross-validation is performed to evaluate the model.
- **Metrics used**: Mean Absolute Error (MAE), Mean Squared Error (MSE), and Root Mean Squared Error (RMSE).

## Visualization

Scatter plot to visualize actual vs predicted values.

## Results

- **Best parameters** found through GridSearchCV.
- **Evaluation metrics**: MAE, MSE, RMSE.
- Actual vs predicted values plot.

## Contributing

If you would like to contribute to this project, please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add new feature'`).
5. Push to the branch (`git push origin feature-branch`).
6. Open a pull request.

---

This README provides a comprehensive overview of the project, from data preprocessing and geocoding to model training and evaluation. It ensures that anyone interested in the project can easily understand and replicate the process.
