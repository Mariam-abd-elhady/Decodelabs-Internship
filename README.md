# 🏠 House Rent Prediction Analysis

## Project Overview
This project focuses on analyzing house rent data and predicting rental prices using various regression techniques. The dataset contains multiple features that influence rental prices, including property characteristics, location factors, and amenities. The goal is to develop accurate models for rent prediction that can assist both tenants and landlords in determining fair rental prices.

## Dataset
The `House_Rent_Dataset.csv` dataset was used, which contains rental information from various cities in India. The dataset includes:
- Property features (BHK, Size, Bathroom, Floor)
- Location information (City, Area Locality, Area Type)
- Furnishing status (Furnished, Semi-Furnished, Unfurnished)
- Tenant preferences (Bachelors, Family, Bachelors/Family)
- Point of contact information
- Posted date

## Data Processing Steps
1. **Handling missing values**: Removed rows with null values
2. **Encoding categorical variables**: 
   - Used One-Hot Encoding for City, Area Type, and Point of Contact
   - Used Ordinal Encoding for Furnishing Status and Tenant Preferred
3. **Feature engineering**:
   - Target encoding for Area Locality (using mean rent)
   - Converted Posted On to datetime and extracted integer representation
   - Parsed Floor information to extract numeric floor numbers
4. **Feature scaling**: Applied MinMaxScaler to the Size feature
5. **Outlier removal**: Removed outliers from BHK feature using IQR method
6. **Data splitting**: Split into training (80%) and testing (20%) sets

## Machine Learning Models Used
The following regression models were implemented and evaluated:
- Linear Regression
- Lasso Regression
- Ridge Regression
- K-Nearest Neighbors (KNN)
- Decision Tree
- Random Forest
- ExtraTrees
- Bagging Regressor
- AdaBoost Regressor
- Gradient Boosting Regressor
- HistGradientBoosting Regressor
- XGBoost
- CatBoost
- LightGBM

## Evaluation Metrics
The models were evaluated using:
- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R-squared (R²) Score

## Results

| Model | MAE Test | RMSE Test | R² Test |
|-------|----------|-----------|---------|
| Decision Tree | 12,525.87 | 98,542.37 | 0.4026 |
| Ridge | 15,777.71 | 100,312.74 | 0.3810 |
| Lasso | 15,928.54 | 100,346.50 | 0.3806 |
| Linear Regression | 15,939.45 | 100,349.65 | 0.3805 |
| Bagging | 11,671.23 | 103,320.63 | 0.3433 |
| Random Forest | 11,773.10 | 103,564.49 | 0.3402 |
| HistGradientBoosting | 11,712.94 | 105,191.20 | 0.3193 |
| LightGBM | 11,906.60 | 106,558.86 | 0.3015 |
| GradientBoosting | 12,733.58 | 107,276.65 | 0.2920 |
| ExtraTrees | 10,755.19 | 108,393.64 | 0.2772 |
| CatBoost | 12,021.94 | 108,483.94 | 0.2760 |
| XGBoost | 11,927.04 | 108,945.47 | 0.2699 |
| AdaBoost | 17,840.86 | 109,784.76 | 0.2586 |
| KNN | 14,813.77 | 114,718.84 | 0.1904 |

## Key Insights
The Decision Tree model achieved the highest R² score of 0.4026 on the test set, indicating it captured approximately 40% of the variance in rental prices. Traditional linear models (Linear Regression, Lasso, Ridge) performed similarly with R² scores around 0.38. Ensemble methods like Random Forest and Gradient Boosting showed moderate performance with R² scores between 0.27-0.34. The relatively low R² scores suggest that rental prices are influenced by factors not captured in the current dataset, such as property condition, exact location within a neighborhood, seasonal variations, and economic factors.

## Requirements
- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- xgboost
- lightgbm
- catboost
- tqdm

## Author
Mariam-abd-elhady
