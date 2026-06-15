# Smart Crowd Forecasting for Bengaluru Metro Stations using ML

An end-to-end Machine Learning project to predict passenger crowd levels across Purple, Green and Yellow metro lines in Bengaluru using real-world inspired data.

---

## Problem Statement

Bengaluru Metro (BMRCL) faces overcrowding during peak hours at key stations like Majestic, MG Road and Indiranagar. This project predicts passenger count and crowd level to help metro authorities optimize train frequency and reduce overcrowding.

---

## Project Demo

> Input: Station Name, Hour, Day, Weather
> Output: Predicted Passenger Count + Crowd Level (Low / Medium / High)

---

## Dataset Details

| Detail | Value |
|--------|-------|
| Total Rows | 3000 |
| Total Columns | 21 |
| Metro Lines | Purple, Green, Yellow |
| Stations | 40+ real BMRCL stations |
| Source | Synthetic data based on real BMRCL station network and realistic ridership patterns |
| Target 1 | passenger_count (Regression) |
| Target 2 | Passenger_Crowd_Level (Classification) |

### Features Used

| Feature | Description |
|---------|-------------|
| station_name | Real BMRCL station name |
| metro_line | Purple / Green / Yellow |
| hour_of_day | Hour from 6 AM to 10 PM |
| day_of_week | Monday to Sunday |
| month | January to December |
| is_weekend | Yes or No |
| is_holiday | Yes or No |
| temperature_c | Temperature in Celsius |
| is_raining | Yes or No |
| nearby_it_park | Yes or No |
| train_frequency_min | 3 / 5 / 8 minutes |
| is_peak_hour | Yes or No |
| time_category | Morning / Midday / Evening / Night |
| is_off_day | Yes or No |
| fare_inr | Fare in Indian Rupees |
| delay_minutes | Train delay in minutes |
| wifi_available | Yes or No |
| station_type | Regular / Terminal / Interchange |

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.10 | Programming Language |
| Pandas | Data Manipulation |
| NumPy | Numerical Computing |
| Matplotlib | Data Visualization |
| Seaborn | Statistical Plots |
| Scikit-learn | ML Algorithms |
| XGBoost | Gradient Boosting |
| Pickle | Model Saving |
| Streamlit | Web Deployment |
| GitHub | Version Control |

---

## Project Pipeline

```
Data Loading
    |
Data Cleaning (Missing Values, Duplicates, Outliers)
    |
Encoding (Label Encoding, Binary Encoding)
    |
EDA (8 Visualizations)
    |
Feature Scaling (StandardScaler)
    |
Feature Selection
    |
Train Test Split (80% / 20%)
    |
Model Training
    |-- Regression  : Linear Regression, Random Forest, XGBoost
    |-- Classification: Logistic Regression, Random Forest, XGBoost
    |
Model Evaluation and Comparison
    |
Model Saving (Pickle)
    |
Streamlit Deployment
```

---

## Model Results

### Regression (Predict passenger_count)

| Model | R2 Score | MAE | RMSE |
|-------|----------|-----|------|
| Linear Regression | 0.73 | -- | -- |
| Random Forest | 0.88 | -- | -- |
| XGBoost | 0.91 | -- | -- |

### Classification (Predict Crowd Level)

| Model | Accuracy |
|-------|----------|
| Logistic Regression | ~82% |
| Random Forest | ~91% |
| XGBoost | ~93% |

> Best Model: XGBoost (both Regression and Classification)

---

## Data Cleaning Steps

1. Drop rows with critical missing values (station_name, metro_line, passenger_count)
2. Fill temperature_c with Mean
3. Fill train_frequency_min, delay_minutes, fare_inr, passenger_count with Median
4. Fill Yes/No columns with No
5. Fill categorical columns with Mode
6. Fix date column format to MM-DD-YYYY
7. Verify zero missing values remaining

---

## Project Structure

```
bengaluru-metro-crowd-prediction/
|
|-- data/
|   |-- Bengaluru_Metro_Final.csv        Raw dataset
|
|-- notebooks/
|   |-- Bengaluru_Metro.ipynb            Main project notebook
|
|-- models/
|   |-- model_regression.pkl             Saved XGBoost Regression model
|   |-- model_classification.pkl         Saved XGBoost Classification model
|
|-- app/
|   |-- app.py                           Streamlit web app
|
|-- README.md                            Project documentation
|-- requirements.txt                     All required libraries
```

---

## How to Run Locally

### Step 1 - Clone the repository
```
git clone https://github.com/Me-Nandhakumar/bengaluru-metro-crowd-prediction.git
cd bengaluru-metro-crowd-prediction
```

### Step 2 - Install required libraries
```
pip install -r requirements.txt
```

### Step 3 - Open the notebook
```
jupyter notebook notebooks/Bengaluru_Metro.ipynb
```

### Step 4 - Run the Streamlit app
```
streamlit run app/app.py
```

---

## Requirements

```
pandas
numpy
matplotlib
seaborn
scikit-learn
xgboost
streamlit
pickle
jupyter
```

---

## Key Insights from EDA

- Peak hours (7 to 9 AM and 5 to 7 PM) have 2 to 3 times more passengers than off-peak hours
- Majestic and MG Road stations have the highest crowd levels
- Weekday passenger count is higher than weekends by approximately 35%
- Rainy days reduce passenger count by approximately 20%
- Stations near IT parks see sharp spikes during office hours
- Yellow line stations show growing ridership due to Electronic City connectivity

---

## Future Enhancements

- Real-time metro data integration via BMRCL API
- Advanced time series forecasting using LSTM models
- Interactive dashboards with Plotly
- Cloud deployment using Streamlit Cloud
- Incorporation of live weather and event data for improved accuracy
- Mobile app integration

---

## Author

**Nandhakumar S**
Python Developer | Machine Learning Engineer
Bengaluru, Karnataka, India

- GitHub: [Me-Nandhakumar](https://github.com/Me-Nandhakumar)
- LinkedIn: [Nandhakumar-SJ](https://linkedin.com/in/Nandhakumar-SJ)
- Email: nandhakumar.s.jnandhu@gmail.com

---

## License

This project is open source and available under the MIT License.
