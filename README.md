# Bengaluru House Price Prediction

A machine learning project that predicts residential property prices in Bengaluru using a cleaned real-estate dataset and an interactive Streamlit dashboard.

## Overview

This project combines:
- data cleaning and feature engineering on the Bengaluru house dataset
- a trained regression ensemble model
- a Streamlit web app for price prediction
- an exploration notebook for EDA and analysis

The app allows users to enter property attributes such as location, total square feet, number of bathrooms, and BHK, then estimates the expected sale price.

## Features

- Predict home prices based on key property features
- Interactive dashboard built with Streamlit
- Cleaned dataset and preprocessing pipeline
- Ensemble model using Random Forest + Extra Trees + CatBoost
- Visual property insights and valuation output

## Tech Stack

- Python
- Streamlit
- Pandas
- NumPy
- scikit-learn
- CatBoost
- Plotly
- Jupyter Notebook

## Project Structure

```text
Bengaluru_House_Data.csv      # Raw Bengaluru property dataset
cleaned_df.csv                # Cleaned dataset used by the app
train_model.py                # Training pipeline and model serialization
app.py                        # Streamlit application
eda.ipynb                     # Exploratory data analysis notebook
requirements.txt              # Python dependencies
rf_model.joblib               # Trained model
model_columns.joblib          # Input feature columns used at inference
hdlogo.webp                   # Logo asset
house_logo.png                # App logo
```

## Dataset

The raw dataset is stored in `Bengaluru_House_Data.csv` and includes attributes such as:
- location
- size / BHK
- total_sqft
- bath
- price

The training script performs cleaning, outlier removal, feature engineering, and one-hot encoding before training the model.

## Getting Started

### 1. Clone or open the project

```bash
cd "House Price Prediction"
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate it:

- Windows PowerShell:
```powershell
.\.venv\Scripts\Activate.ps1
```

- Windows Command Prompt:
```cmd
.venv\Scripts\activate.bat
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

## Run the App

```bash
streamlit run app.py
```

This launches the interactive housing price prediction dashboard in your browser.

## Train the Model

If the model files are missing or you want to retrain the model:

```bash
python train_model.py
```

This script:
- loads the raw dataset
- cleans and validates fields
- removes inconsistent rows and outliers
- saves `cleaned_df.csv`
- trains a voting regressor ensemble
- saves the trained model and feature columns for inference

## Model Notes

The model used in this project is a weighted ensemble of:
- RandomForestRegressor
- ExtraTreesRegressor
- CatBoostRegressor

The final model is saved as `rf_model.joblib`, and the expected input feature order is saved as `model_columns.joblib`.

## Notes

- The app expects the model files to exist in the project root.
- If you modify preprocessing or feature engineering, retrain the model before running the app.
- The project is intended for Bengaluru residential pricing estimation and may not generalize well to other cities without retraining.

## License

This project is provided as-is for educational and demonstration purposes.
