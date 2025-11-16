# Fortum Energy Consumption Prediction

LightGBM models for predicting electricity consumption:

- **48-hour ahead predictions** (`48hr_LightGBM.ipynb`)
- **12-month ahead predictions** (`12m_LightGBM_model.ipynb`)

## Setup

Install dependencies:

```bash
pip -m venv .venv
pip install -r requirements.txt
.venv/Scripts/activate
```

## Data

Ensure that the CSVs are in the project root.

## Running

### 48-Hour Prediction Model

```bash
jupyter notebook 48hr_LightGBM.ipynb
```

Run all cells sequentially. The notebook:

1. Loads and preprocesses data from `merged.csv`
2. Creates time and lag features
3. Tunes hyperparameters with Optuna
4. Trains final LightGBM model

### 12-Month Prediction Model

```bash
jupyter notebook 12m_LightGBM_model.ipynb
```

Run all cells sequentially. The notebook:

1. Aggregates hourly data to monthly
2. Creates monthly features and lags
3. Trains 12 separate models (one for each month ahead)
4. Models saved in `12 month prediction model weights/`

## Model Weights

- `48hr_weights.txt` - 48-hour model weights
- `12m_weights/` - 12 monthly model files (lightgbm_model_1.txt through lightgbm_model_12.txt)
