# California Housing Price Prediction

## Project Overview
This project predicts median housing prices in California districts using machine learning. The model analyzes location, housing characteristics, and socioeconomic factors to estimate property values.

## Dataset
- **Source**: California Housing Prices from Kaggle
- **Records**: 20,640
- **Features**: 9 numerical + 1 categorical
- **Target Variable**: `median_house_value`

## Data Preprocessing
### Handling Missing Values
- Imputed missing `total_bedrooms` using median values
- Dropped duplicate entries

### Feature Engineering
- Created new features:
  - Rooms per household
  - Bedrooms per room ratio
  - Population per household

### Outlier Treatment
- Applied IQR method for skewed features
- Used Z-score for normally distributed features

## Exploratory Data Analysis
### Key Insights
- Strong positive correlation (0.69) between income and house value
- Coastal properties command 2.5× higher prices than inland
- Most homes built between 1940-2000 (median age 29 years)

## Model Performance Comparison

| Model | R² Score | 
|-------|----------|-------------|
| Linear Regression (LR) | 63.11% | 
| Random Forest Regressor (RFR) | 81.99% | 
| XGBoost Regressor (XGB) | 81.99% | 

### Key Observations:
- **Random Forest and XGBoost** show nearly identical performance (81.99% R²)
- **Linear Regression** underperforms by ~19 percentage points
- Both ensemble methods outperform the baseline by ~18.9%

### Recommendation:
Since XGBoost and Random Forest perform equally well in this case:
1. **Choose XGBoost** if you need faster predictions on new data
2. **Choose Random Forest** if model interpretability is more important
3. Consider hyperparameter tuning to push performance beyond 82%

## How to Run
1. Install dependencies:
```bash
pip install -r requirements.txt
