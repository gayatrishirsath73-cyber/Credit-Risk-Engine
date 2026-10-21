# Credit Risk Engine

A machine-learning project that estimates loan-default risk using a Random Forest classifier and a Streamlit dashboard.

## Features

- Data ingestion and data cleaning
- Exploratory data analysis and visualizations
- Feature engineering and categorical encoding
- Random Forest model training and evaluation
- Saved model and feature names for consistent predictions
- Interactive customer-input dashboard
- Predicted loan-default class and estimated probability

## Technology Stack

- Python
- Pandas
- Scikit-learn
- Joblib
- Streamlit
- Matplotlib and Seaborn

## Run Locally

1. Clone this repository.
2. Create and activate a virtual environment.
3. Install dependencies:

   `pip install -r requirements.txt`

4. Start the dashboard:

   `streamlit run streamlit_app.py`

## Model

The application loads the trained model from:

`artifacts/models/loan_rf_model.joblib`

If this file is not included in the repository, train the model first using `train_pipeline.py`.

## Disclaimer

This project is an educational prototype. Predictions are estimates and should not be used as the sole basis for real-world lending decisions.
