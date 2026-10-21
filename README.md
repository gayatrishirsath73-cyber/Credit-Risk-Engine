# 💳 Credit Risk Engine

### Machine Learning-Based Loan Default Risk Prediction System

## 📌 Overview

The **Credit Risk Engine** is a machine learning-based application designed to estimate the likelihood of loan default using customer financial information, credit history, employment details, and loan characteristics.

The system uses a **Random Forest Classifier** trained on a structured loan dataset. It includes a data processing pipeline, exploratory data analysis (EDA), feature engineering, model evaluation, and an interactive Streamlit dashboard.

Users can enter customer and loan details through the dashboard to obtain a predicted loan-default class and, when available, an estimated default probability.

---

## ✨ Features

- Loan default prediction using a Random Forest model
- Interactive Streamlit dashboard
- Customer financial information analysis
- Credit history and loan profile assessment
- Automated handling of missing values and duplicate records
- Categorical feature encoding
- Exploratory data analysis with visualizations
- Train-test splitting and model evaluation
- Classification report generation
- Saved model artifact for consistent predictions
- Estimated default probability display
- Organized and modular Python project structure

---

## 📊 Dataset

The project uses a structured loan dataset containing **10,000 records and 32 columns**, including customer financial attributes, credit history, loan information, and the target variable.

### Important Features

- Age and gender
- Monthly income and expenses
- Savings balance
- Existing loan amount
- Credit card utilization
- Debt-to-income ratio
- Credit score
- Previous loan defaults
- Payment delay days
- Credit history duration
- Loan amount requested
- Loan tenure and interest rate
- EMI and EMI-to-income ratio
- Employment type and education level
- Document verification score
- Address and job stability

**Target variable:** `Loan_Default`

- `Yes` — Loan default
- `No` — No loan default

The dataset is stored at:

`artifacts/data/raw/loan_guard_dataset.csv`

> **Privacy note:** Use only synthetic or appropriately anonymized data in a public repository. Never publish real customer financial or personally identifiable information.

---

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Pandas | Data manipulation and preprocessing |
| Scikit-learn | Random Forest training and evaluation |
| Joblib | Saving and loading the trained model |
| Streamlit | Interactive web dashboard |
| Matplotlib | Data visualization |
| Seaborn | Exploratory data analysis |
| Git and GitHub | Version control and project hosting |

---

## 📁 Project Structure

```text
Credit-Risk-Engine/
│
├── artifacts/
│   ├── data/
│   │   ├── raw/
│   │   │   └── loan_guard_dataset.csv
│   │   └── processed/
│   │
│   ├── models/
│   │   └── loan_rf_model.joblib
│   │
│   └── visuals/
│       ├── Univariate Analysis - Categorical Variables Composition.png
│       ├── Univariate Analysis - Numerical Variables Distribution.png
│       ├── BI-Variate Analysis - Categorical Variables vs Target Variable Distribution.png
│       └── BI-Variate Analysis - Numerical Variables vs Target Variable Distribution.png
│
├── src/
│   └── credit_risk/
│       ├── __init__.py
│       ├── data_ingestion.py
│       ├── data_eda.py
│       ├── logger.py
│       └── model_trainer.py
│
├── streamlit_app.py
├── train_pipeline.py
├── requirements.txt
├── README.md
└── .gitignore
```

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/gayatrishirsath73-cyber/Credit-Risk-Engine.git
cd Credit-Risk-Engine
```

### 2. Create a virtual environment

```bash
python -m venv credit_risk_env
```

### 3. Activate the environment

**Windows PowerShell:**

```powershell
.\credit_risk_env\Scripts\Activate.ps1
```

**Windows Command Prompt:**

```cmd
credit_risk_env\Scripts\activate.bat
```

**macOS/Linux:**

```bash
source credit_risk_env/bin/activate
```

### 4. Install dependencies

```bash
python -m pip install -r requirements.txt
```

---

## 🔍 Exploratory Data Analysis

The project includes exploratory data analysis to understand the dataset before model training.

The analysis covers:

- Numerical variable distributions
- Categorical variable composition
- Relationships between features and loan defaults
- Data quality and missing-value handling
- Duplicate record removal

Generated visualizations are stored in:

`artifacts/visuals/`

---

## 🧹 Data Preprocessing and Feature Engineering

The preprocessing pipeline performs the following operations:

1. Loads the loan dataset.
2. Removes duplicate records.
3. Handles missing numerical values using median imputation.
4. Handles missing categorical values using mode imputation.
5. Separates the target variable from the input features.
6. Drops unnecessary customer identifier columns.
7. Converts categorical variables into numerical dummy features using Pandas.
8. Splits the dataset into training and testing sets.

The current model uses an 80:20 train-test split with stratification and a fixed random state for reproducibility.

---

## 🤖 Model Training

The project uses a **Random Forest Classifier**, an ensemble learning algorithm that combines predictions from multiple decision trees.

### Model Configuration

- **Algorithm:** Random Forest Classifier
- **Number of estimators:** 100 trees
- **Random state:** 42
- **Training split:** 80%
- **Testing split:** 20%
- **Evaluation:** Classification report
- **Target classes:** `No` and `Yes`

### Run the training pipeline

From the project root, execute:

```bash
python train_pipeline.py
```

The pipeline loads and cleans the dataset, performs EDA, prepares features, trains the model, evaluates predictions, and saves the model artifact.

### Saved Model

```text
artifacts/models/loan_rf_model.joblib
```

The saved artifact contains the trained model and the ordered feature names required for prediction consistency.

---

## 🚀 Run the Application

Start the Streamlit dashboard from the project root:

```bash
streamlit run streamlit_app.py
```

Alternatively:

```bash
python -m streamlit run streamlit_app.py
```

Open the local URL displayed in the terminal. The default Streamlit address is:

[http://localhost:8501](http://localhost:8501)

If the default port is already occupied, Streamlit may use another port, such as `8502`.

---

## 📈 Prediction Output

The dashboard provides:

- Predicted loan-default class
- Estimated probability of default, when supported by the model
- Customer financial input summary
- Credit profile and loan-related inputs
- Model prediction results

The predicted probability is the model's estimated probability, not a guarantee that a borrower will default.

---

## ☁️ Deployment

The project can be deployed using **Streamlit Community Cloud**.

### Deployment Steps

1. Push the project to GitHub.
2. Ensure `requirements.txt` contains compatible dependencies.
3. Confirm that `streamlit_app.py` and the saved model artifact are available in the repository.
4. Visit [Streamlit Community Cloud](https://share.streamlit.io/).
5. Sign in using GitHub.
6. Create a new app and select the `Credit-Risk-Engine` repository.
7. Select the `main` branch.
8. Set the main file path to `streamlit_app.py`.
9. Deploy and test the public application URL.

The deployment environment must use compatible Python and scikit-learn versions for the saved model.

---

## 🔐 Limitations and Responsible Use

- Model performance depends on the quality and representativeness of the training dataset.
- Predictions may be affected by data imbalance, bias, or missing information.
- Estimated probabilities may require calibration before practical use.
- The current pipeline uses median and mode imputation before the train-test split, which can introduce data leakage into evaluation. A production implementation should fit preprocessing only on the training data.
- The system is an educational prototype and should not be used as the sole basis for real lending decisions.

---

## 🔮 Future Scope

- Deploy the dashboard on a cloud platform
- Improve model evaluation with ROC-AUC, precision, recall, and F1-score
- Add explainable AI using SHAP or feature importance
- Introduce cross-validation and hyperparameter tuning
- Improve missing-value handling through a reusable preprocessing pipeline
- Add database integration and secure user authentication
- Improve model monitoring and fairness assessment
- Add downloadable prediction reports
- Develop APIs for integration with other applications

---

## 👩‍💻 Author

**Gayatri Shirsath**

GitHub: [gayatrishirsath73-cyber](https://github.com/gayatrishirsath73-cyber)

---

## 📜 Disclaimer

This project is intended for educational and demonstration purposes. Its predictions are estimates based on a machine learning model and should not be interpreted as financial advice, a credit approval decision, or a guarantee of future loan repayment behavior.
