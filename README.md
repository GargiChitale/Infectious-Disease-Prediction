# COVID-19 Cases Prediction in India

This project aims to predict COVID-19 cases in India using a dataset from Kaggle. The data includes information on COVID-19 cases, population density, travel patterns, and healthcare facilities across different states and union territories of India.

## Dataset Information

The dataset is sourced from Kaggle and consists of three main files:
- `covid_19_india.csv`
- `HospitalBedsIndia.csv`
- `population_india_census2011.csv`

[Link to Dataset](https://www.kaggle.com/code/parulpandey/tracking-india-s-coronavirus-spread/notebook#Part-1:-Analysing-the-present-condition-in-India)

## Project Steps

### 1. Data Loading and Merging
- Three datasets are loaded: `covid_19_india.csv`, `HospitalBedsIndia.csv`, and `population_india_census2011.csv`.
- Data from these datasets are merged using the 'State/UT' column.

### 2. Data Preprocessing
- The 'Time' column is dropped from the `covid_data` DataFrame.
- The 'Sno_y' column is dropped from the `merged_data` DataFrame.
- The 'Date' column is converted to a datetime object.
- Missing values are replaced with NaN.
- The 'Density' column is extracted to retain only numeric values.
- Numeric columns are filled with the median value.

### 3. Feature Engineering
- A new column `TotalHealthcareBeds` is created by summing up different types of healthcare beds.

### 4. Model Training
- Features (X) and target variable (y) are defined.
- The dataset is split into training and testing sets.
- A linear regression model is trained using `X_train` and `y_train`.

### 5. Model Evaluation
- Predictions are made on both the training and testing sets.
- Root Mean Squared Error (RMSE) and R-squared values are calculated for both sets to evaluate the model's performance.
  - RMSE is a measure of the average deviation of the predicted values from the actual values.
  - R-squared is a measure of how well the model explains the variance in the target variable.

### 6. New Data Prediction
- A new DataFrame (`new_data`) is created with hypothetical values.
- The trained model is used to predict the number of COVID-19 cases for the new data.

## How to Run

1. **Setup**:
   - Ensure you have Python installed on your system.
   - Clone the repository and navigate to the project directory.

2. **Dependencies**:
   - Install necessary dependencies. You might use `pip` to install required packages:
     ```sh
     pip install -r requirements.txt
     ```

3. **Running the Scripts**:
   - Execute the data processing and model training script:
     ```sh
     python main.ipynb
     ```

4. **Prediction**:
   - Follow the instructions in the script to input hypothetical values and make predictions.

