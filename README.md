Forecasting Mean Temperature — London Time Series Project

A reproducible, well-documented project for time-series forecasting of daily mean temperature.
This repository contains the code, data-processing pipelines, trained models, evaluation notebooks, and a simple Streamlit demo used in the course report.

Project overview

This project builds and compares multiple forecasting approaches to predict daily mean temperature for London. It is designed to show end-to-end workflow skills you can present to recruiters: data ingestion, cleaning, feature engineering, model training, hyperparameter tuning, evaluation, and a minimal demo.

Key goals:

Demonstrate practical skills in time-series preprocessing and modeling.

Compare classical and ML approaches (Prophet, ARIMA variants, Linear Regression, Random Forest, XGBoost, LightGBM, SVR, LSTM).

Provide reproducible experiments and clear evaluation metrics (MAE, MSE/RMSE, MAPE, R²).

Package a lightweight demo so reviewers can interact with the models.

Highlights / Key results

Baseline Prophet (univariate) — MAE ≈ 2.29 °C, R² ≈ 0.76.

Improved Prophet with external regressors — MAE ≈ 0.78 °C, R² ≈ 0.97.

Best classical/ensemble models (LightGBM / XGBoost / Bayesian Ridge) achieved R² ≈ 0.89–0.97 and MAE typically < 1.6 °C depending on features and preprocessing.
(Detailed metrics and plots are available in the project report and notebooks.)

What’s included in this repo

SourceCode.zip — main source code and scripts (training, preprocessing, model wrappers).

report/ — final written report and visualizations (figures, metric tables).

notebooks/ — Jupyter notebooks used for exploration, model training, and evaluation.

data/ — instructions and sample script to fetch/prepare the dataset (raw data not always included — see data section).

models/ — saved model artifacts (pickle / keras h5).

demo/ — Streamlit demo app (app.py) to visualize forecasts and compare models.

checklist.md — project checklist and reproducibility checklist used during development.

README.md — (this file) quick-start and reproduction instructions.

Data

The primary input is the historical London weather table (daily observations: date, min_temp, max_temp, mean_temp, sunshine, cloud_cover, pressure, precipitation, snow_depth, global_radiation, …). The dataset used in the work was originally downloaded from the public data platform Kaggle (see report for the exact dataset identifier and license).
Note: Raw data may be large and/or subject to the dataset owner’s terms — the repository contains scripts to re-download and preprocess the exact files used in experiments.

Reproducing the results — quick start

Clone the repository

git clone https://github.com/<your-username>/london-temp-forecast.git
cd london-temp-forecast

Unzip source code (if you uploaded a SourceCode.zip separately)

unzip SourceCode.zip -d src

Create Python environment and install

python -m venv .venv
source .venv/bin/activate     # on Windows: .venv\Scripts\activate
pip install -r requirements.txt

Prepare data

# Example (adjust to how you store credentials / dataset):
python src/data/download_dataset.py --target data/raw/london_weather.csv
python src/data/preprocess.py --in data/raw/london_weather.csv --out data/processed/df_processed.csv

Train a model (example: LightGBM)

python src/train.py --config configs/lightgbm_config.yaml

Evaluate & reproduce figures

python src/evaluate.py --model models/lightgbm_best.pkl --test data/processed/test.csv
# or open notebooks:
jupyter lab notebooks/Model_Comparison.ipynb

Run the demo (interactive)

# start Streamlit demo
streamlit run demo/app.py

The demo uses a minimal front-end to choose year & model and shows forecast vs actual.

Repository structure (short)
.
├─ data/                    # data download & preprocess scripts
├─ src/                     # core source code (train, predict, utils)
├─ notebooks/               # EDA and experimental notebooks
├─ models/                  # saved models and artifacts
├─ demo/                    # Streamlit demo app
├─ report/                  # final PDF report & figures
├─ requirements.txt
├─ checklist.md
└─ SourceCode.zip
Modeling notes & best practices (for recruiters)

Modeling diversity: The project intentionally compares statistical (Prophet, ARIMA) and machine learning (LightGBM, XGBoost, RandomForest, SVR, Bayesian Ridge) as well as deep learning (LSTM) approaches to highlight trade-offs in interpretability, runtime, and accuracy.

Feature engineering: Rolling windows, calendar features (day/month/week), lag features, and selected meteorological regressors were used to boost predictive power, especially for short-term variations.

Validation strategy: Time-aware train/test splits (no leakage), and optional walk-forward validation for robust error estimation.

Reproducibility: All experiments are driven by config files; random seeds are fixed and package versions are captured in requirements.txt.

How to present this project in interviews

Start with the problem statement: forecasting daily mean temperature for a major city and why it matters (urban planning, energy, agriculture).

Explain the data pipeline: raw -> cleaned -> features -> train/test split.

Outline models tried, why each was chosen, and the key metrics you used to compare them.

Show visual evidence: one or two plots (forecast vs actual; residual analysis) and a short demo (Streamlit).

Finish with lessons learned and concrete next steps (e.g., probabilistic forecasts, ensemble stacking, deployment suggestions).

Demo & dependencies

The demo is implemented with the Streamlit framework. To run it locally, install requirements and call:

streamlit run demo/app.py

(If you prefer a containerized run, add a simple Dockerfile — instructions are in demo/readme.md.)

Framework used for demo: Streamlit.

Credits & authorship

Author: Cao Quang Dang — code, experiments, report.

Advisor: Tran Ngoc Thang.

Institutional affiliation: Hanoi University of Science and Technology.
(Full acknowledgements and the final report are included in the report/ folder.)

License

This project is released under the MIT License — see LICENSE for details.
