# German Credit Risk Analysis

A comprehensive machine learning project for predicting credit risk using the German Credit Dataset.

## Project Structure

```
CreditRisk/
├── Content/
│   ├── App/                    # Streamlit web application
│   │   └── app.py
│   ├── data/                   # Data directory
│   │   ├── raw/               # Original dataset
│   │   └── Processed/         # Cleaned data for Power BI
│   ├── Models/                # Trained models and encoders
│   │   ├── extra_trees_credit_model.pkl
│   │   └── *_encoder.pkl
│   └── notebooks/             # Jupyter notebooks
│       ├── analysis_model.ipynb
│       └── powerbi_data_prep.ipynb
├── .gitignore
└── README.md
```

## Features

- **Exploratory Data Analysis (EDA)**: Comprehensive analysis of credit risk factors
- **Machine Learning Models**: Comparison of Decision Tree, Random Forest, Extra Trees, and XGBoost
- **Web Application**: Interactive Streamlit app for credit risk prediction
- **Power BI Ready**: Cleaned dataset with business-friendly labels for dashboard creation

## Dataset

The German Credit Dataset contains 1000 credit applications with 10 features including:
- Demographics (Age, Sex, Job, Housing)
- Financial Status (Saving accounts, Checking account)
- Loan Details (Credit amount, Duration, Purpose)
- Risk Classification (Good/Bad)

## Models Performance

| Model | Accuracy |
|-------|----------|
| Random Forest | 77.0% |
| Extra Trees | 74.5% |
| XGBoost | 73.5% |
| Decision Tree | 70.5% |

## Installation

### Requirements
- Python 3.8+
- Jupyter Notebook
- Streamlit

### Setup

1. Clone the repository:
```bash
git clone https://github.com/mattlkz/credit-risk-analysis.git
cd credit-risk-analysis
```

2. Install dependencies:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost streamlit joblib
```

## Usage

### Running the Notebooks

Navigate to the notebooks directory:
```bash
cd Content/notebooks
jupyter notebook
```

### Running the Web Application

Navigate to the App directory:
```bash
cd Content/App
streamlit run app.py
```

### Power BI Dashboard

The cleaned dataset is available at:
- `Content/data/Processed/german_credit_data_powerbi.csv`
- `Content/data/Processed/data_dictionary_powerbi.csv`

## Key Insights

- **Bad Risk Indicators:**
  - Younger age (avg 34 vs 36 years)
  - Higher credit amounts (avg $3,938 vs $2,985)
  - Longer durations (avg 24.9 vs 19.2 months)

- **Correlations:**
  - Strong correlation (0.62) between Credit amount and Duration
  - Job level moderately correlates (0.29) with Credit amount

## Project Workflow

1. **Data Exploration** (`analysis_model.ipynb`)
   - Load and analyze the German Credit Dataset
   - Visualize distributions and relationships
   - Identify risk factors

2. **Model Training** (`analysis_model.ipynb`)
   - Encode categorical variables
   - Train multiple classification models
   - Compare performance metrics

3. **Power BI Preparation** (`powerbi_data_prep.ipynb`)
   - Clean and transform data
   - Create business-friendly labels
   - Generate calculated metrics

4. **Deployment** (`app.py`)
   - Load trained model
   - Create interactive prediction interface
   - Deploy with Streamlit

## License

This project is available for educational purposes.

## Contact

For questions or feedback, please open an issue on GitHub.
