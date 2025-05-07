# Smart Factory Energy Prediction Challenge

## Problem Overview

This project focuses on predicting equipment energy consumption in a smart factory using machine learning. The goal is to:
1) Clean and preprocess sensor data.
2) Identify key factors affecting energy usage.
3) Build and evaluate predictive models.
4) Provide actionable insights to reduce energy consumption.


## Repository Structure

This repository is organized as follows:

```
│── data/  
│   └── data.csv        # Raw dataset 
├── docs/               # Documentation files
│   └── data_description.md  # Detailed description of all features                 
│── smart_factory_energy_prediction.py  # Main Python script  
│── README.md                    # This file  
```
## 🔧 Installation & Setup

### Prerequisites
- Python 3.8+

### Required Libraries

Install the necessary libraries using pip:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn xgboost
```

### How to Run 
Follow these steps to run the project:
1) Clone the repository:

```bash
git clone https://github.com/potluripravith/DS-Intern-Assignment-PotluriPravith.git
```
2) Navigate to the project directory:
```bash
cd DS-Intern-Assignment-PotluriPravith
```
3) Run the script:
```bash
python smart_factory_energy_prediction.py
```
##  Key Steps in the Analysis

### 1. Data Cleaning & Preprocessing
-  Handled missing values using **time-based interpolation**.
-  Removed **negative energy readings** caused by sensor errors.
-  Capped **outliers using the IQR method** to reduce skewness.

### 2. Feature Engineering
-  Created **temperature differential features** (e.g., `zoneX_temp - outdoor_temp`) to better reflect HVAC workload.
-  Computed **rolling statistics** (4-hour mean & standard deviation) to capture short-term trends in energy usage.

### 3. Model Training & Evaluation
-  Evaluated the following **six regression models**:
  - Linear Regression
  - Ridge Regression
  - Lasso Regression
  - Random Forest Regressor
  - Gradient Boosting Regressor
  - XGBoost Regressor
###  Model Performance Comparison

| Model               | RMSE  | MAE   | R²   |
|---------------------|-------|-------|------|
| Gradient Boosting   | 19.48 | 12.30 | 0.77 |
| Linear Regression   | 19.87 | 12.56 | 0.76 |
| Ridge Regression    | 19.87 | 12.56 | 0.76 |
| Lasso Regression    | 19.87 | 12.55 | 0.76 |
| Random Forest       | 20.05 | 12.47 | 0.76 |
| XGBoost             | 21.28 | 12.83 | 0.73 |

---

## Results & Insights

### 🔍 Top Findings
-  **Temperature control** has a significant impact on overall energy consumption.
-  **Time-based features**, such as hour of the day and rolling averages, greatly improve model accuracy.
-  **Sensor anomalies** (e.g., negative readings or extreme spikes) are likely indicators of malfunctioning equipment.

## Recommendations
1) Reduce temperature differentials between zones and outdoors.
2) Monitor high-consumption periods (rolling mean helps detect anomalies).
3) Add more sensor data (equipment status, production load).

## Conclusion
The Gradient Boosting model (R²=0.77) provides reliable predictions for energy consumption. Key takeaways:
1) Temperature management is crucial for reducing energy use.
2) Time-based features improve prediction accuracy.
3) Real-time monitoring can help optimize energy efficiency.