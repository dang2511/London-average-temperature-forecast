# 🌡️ London Mean Temperature Forecasting

An end-to-end time series forecasting project predicting daily mean temperature using multiple statistical, machine learning, and deep learning models.

---

## 📌 Project Overview

This project aims to forecast daily mean temperature using historical weather data from London.  

The repository demonstrates:

- Time series preprocessing
- Feature engineering with lag & rolling features
- Multiple forecasting models
- Model performance comparison
- Interactive deployment using Streamlit

This project highlights both analytical thinking and practical machine learning implementation.

---

## 📂 Repository Structure

```
.
├── Prophet.ipynb
├── LightGBM.ipynb
├── XGBOOST.ipynb
├── Random_Forest.ipynb
├── SVR.ipynb
├── Linear_Regression.ipynb
├── Bayesian_Ridge_Regressor.ipynb
├── LSTM.ipynb
├── app.py
└── london_weather.csv
```

---

## 📊 Dataset

- File: `london_weather.csv`
- Contains historical daily weather data including:
  - date
  - mean_temp
  - min_temp
  - max_temp
  - sunshine
  - cloud_cover
  - pressure
  - precipitation
  - snow_depth
  - global_radiation

The dataset is used for training and evaluating forecasting models.

---

## 🔬 Models Implemented

### 1️⃣ Statistical Model
- Prophet

### 2️⃣ Machine Learning Models
- Linear Regression
- Bayesian Ridge Regressor
- Random Forest
- XGBoost
- LightGBM
- Support Vector Regression (SVR)

### 3️⃣ Deep Learning Model
- LSTM (Long Short-Term Memory)

Each model is implemented in a separate Jupyter Notebook for clarity and experimentation.

---

## 📈 Evaluation Metrics

Models are evaluated using:

- MAE (Mean Absolute Error)
- RMSE (Root Mean Squared Error)
- MAPE (Mean Absolute Percentage Error)
- R² Score

Time-aware train/test splitting is used to avoid data leakage.

---

## 🚀 How to Run the Project

### 1️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

(If requirements.txt is not included, install manually: pandas, numpy, scikit-learn, xgboost, lightgbm, prophet, tensorflow/keras, streamlit, matplotlib, seaborn)

---

### 2️⃣ Run Notebooks

Open Jupyter Notebook:

```bash
jupyter notebook
```

Run any of the model notebooks individually:

- Prophet.ipynb
- LightGBM.ipynb
- XGBOOST.ipynb
- LSTM.ipynb
- etc.

---

### 3️⃣ Run Interactive Demo

```bash
streamlit run app.py
```

The Streamlit application allows:

- Selecting forecasting models
- Visualizing predictions vs actual values
- Comparing model performance interactively

---

## 💡 Technical Highlights

- End-to-end forecasting pipeline
- Feature engineering with lag and rolling statistics
- Comparison across statistical, ML, and deep learning models
- Clean notebook separation per model
- Deployment using Streamlit

---

## 🧠 Skills Demonstrated

- Time Series Forecasting
- Feature Engineering
- Machine Learning Model Comparison
- Deep Learning with LSTM
- Model Evaluation & Interpretation
- Python ML Ecosystem
- Deployment with Streamlit

---

## 👤 Author

Cao Quang Dang  
Data Science / Applied Mathematics  

---

## 📄 License

This project is for academic and portfolio purposes.
