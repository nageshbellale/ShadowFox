# ShadowFox AIML Internship - Beginner Task 2: Boston House Price Prediction

## 🌟 Project Overview
This project fulfills the requirement for the Beginner Level task of the ShadowFox AIML Internship. The core objective was to design, implement, and evaluate a **Regression Model** to accurately predict the median value of owner-occupied homes (`MEDV`) in the Boston area using the provided dataset.

The project demonstrates proficiency in the standard machine learning pipeline: data preprocessing, exploratory data analysis (EDA), model training, and performance evaluation.

## 🎯 Final Model Performance
The problem was solved using the **Random Forest Regressor**, which outperformed simpler linear models typically used for this dataset.

| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| **Model** | Random Forest Regressor | A robust ensemble method chosen for its high accuracy in handling non-linear data. |
| **R-squared (R²)** | **0.8879** | The model explains approximately **88.8%** of the variance in house prices. This indicates a high level of predictive accuracy. |
| **Mean Squared Error (MSE)** | 8.22 | The average squared difference between the actual and predicted prices, demonstrating a low overall prediction error. |

## 🛠️ Technical Methodology

### 1. Data Preprocessing
The initial dataset contained 506 entries with 14 features. Several columns (CRIM, ZN, INDUS, CHAS, AGE, LSTAT) contained missing (`NaN`) values.
* **Imputation Strategy:** Missing numerical values were filled using **median imputation** to ensure robustness against potential outliers and to prepare a clean dataset for training.
* **Data Split:** The clean data was split into **80% training** (404 samples) and **20% testing** (102 samples).

### 2. Exploratory Data Analysis (EDA)
EDA was performed to understand the distribution and correlation of the features. Key findings from the correlation heatmap:
* **Strongest Positive Correlate with Price (`MEDV`):** `RM` (Average number of rooms), suggesting more rooms strongly correlate with higher value.
* **Strongest Negative Correlates with Price (`MEDV`):** `LSTAT` (% lower status of the population) and `PTRATIO` (Pupil-Teacher Ratio), suggesting these factors drive house prices down.

### 3. Model Evaluation
Model performance was confirmed using the R² score and visualized with a scatter plot of Actual vs. Predicted values.
* The plot shows predicted values clustering tightly around the ideal prediction line (Y=X), validating the high R² score.

## 📂 Repository Contents
The repository is structured to easily reproduce the analysis:

boston_price_prediction/ ├── data/ │ └── HousingData.csv # The raw dataset used for the project. ├── notebooks/ │ ├── house_price_exploration.ipynb # The complete Jupyter Notebook with all code. │ ├── actual_vs_predicted_prices.png # Plot 3: Visualization of final model accuracy. │ ├── feature_correlation_heatmap.png # Plot 2: Visualization of feature relationships (EDA). │ └── price_distribution_histogram.png # Plot 1: Visualization of the target variable distribution. └── README.md # Project documentation file.


## 💻 How to Reproduce Results

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/nageshbellale/ShadowFox](https://github.com/nageshbellale/ShadowFox)
    cd ShadowFox/boston_price_prediction
    ```
2.  **Install Dependencies:** Ensure the following Python libraries are installed:
    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn
    ```
3.  **Run the Notebook:** Open and execute all cells in the `house_price_exploration.ipy