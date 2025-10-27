# ShadowFox AIML Internship - Intermediate Task: Car Selling Price Prediction

## 🚀 Project Overview
This project was completed as the Intermediate Level task for the ShadowFox AIML Internship. The objective was to design, implement, and rigorously tune a **Regression Model** to accurately predict the selling price of used cars based on various technical, commercial, and temporal features.

This solution demonstrates proficiency in **Feature Engineering**, **One-Hot Encoding**, and **Hyperparameter Tuning** using Randomized Search.

## 🎯 Final Model Performance
The highly non-linear nature of car pricing was tackled using a Random Forest Regressor, which was fine-tuned to achieve excellent results.

| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| **Model** | Tuned Random Forest Regressor | A robust ensemble model optimized for maximum predictive power. |
| **R-squared (R²)** | **0.9423** | The model explains over **94%** of the variability in car selling prices, indicating extremely high accuracy. |
| **Root Mean Squared Error (RMSE)** | 1.1526 | The average magnitude of the prediction error (in lakhs of Rupees), showing the predictions are close to the actual price. |

## ⚙️ Advanced Methodology

### 1. Feature Engineering
A critical step was deriving a feature that captures the car's depreciation over time:
* **`Years_of_Service`:** Calculated as (Current Year - Manufacturing Year). The original `Year` and `Car_Name` columns were then dropped.

### 2. Data Preprocessing
* **Missing Values:** The dataset was clean with no missing values.
* **Encoding:** All categorical features (`Fuel_Type`, `Seller_Type`, `Transmission`) were converted to a numerical format using **One-Hot Encoding** (`pd.get_dummies`) to prepare them for the model.
* **Data Split:** The dataset was split into an 80% training set (240 samples) and a 20% testing set (61 samples).

### 3. Hyperparameter Tuning (Intermediate Requirement)
To achieve the optimal $\text{R}^2$ score, the model underwent rigorous fine-tuning:
* **Technique:** **RandomizedSearchCV** was used to efficiently explore a large space of hyperparameters (n\_estimators, max\_depth, etc.) with 5-fold cross-validation.
* **Best Parameters Found:** `{'n_estimators': 1000, 'min_samples_split': 2, 'min_samples_leaf': 1, 'max_features': 'sqrt', 'max_depth': 25}`

### 4. Evaluation & Visualization
The model's performance was visually confirmed:
* **Actual vs. Predicted Plot:** The scatter plot (`actual_vs_predicted_prices_tuned.png`) shows predictions clustering extremely close to the diagonal ideal line, confirming the high $\text{R}^2$ score.

## 📂 Repository Contents
The project structure is organized for clarity and reproducibility:

Car_Price_Prediction/ ├── data/ │ └── car.csv # The raw dataset. ├── notebooks/ │ └── car_price_prediction_analysis.ipynb # The complete Jupyter Notebook (code and output). ├── visuals/ │ ├── actual_vs_predicted_prices_tuned.png # Final model performance plot. │ ├── years_vs_price_scatter.png # EDA: Price vs. Car Age. │ └── present_vs_price_scatter.png # EDA: Price vs. Showroom Price. └── README.md # Project documentation.


## 🔗 How to Reproduce Results
1.  **Clone the Repository.**
2.  **Navigate** to the `Car_Price_Prediction` folder.
3.  **Install Dependencies:** Ensure you have the standard data science stack (Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn).
4.  **Run the Notebook:** Execute all cells in the `car_price_prediction_analysis.