# Customer Churn Prediction

A Streamlit application that uses an artificial neural network (ANN) to estimate whether a bank customer is likely to churn.

## Features

- Interactive customer input form
- Geography one-hot encoding
- Gender label encoding
- Feature scaling with the fitted scaler
- ANN prediction probability and churn classification

## Requirements

- Python 3.9 or newer
- The packages listed in `requirements.txt`

## Setup

Create and activate a virtual environment from the project directory:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

Install the dependencies:

```powershell
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## Run the app

Start Streamlit from the project directory so the model and preprocessing files are resolved correctly:

```powershell
streamlit run app.py
```

The app opens a browser page where you can enter customer details and view the predicted churn probability.

## Runtime files

The application expects these files in the project root:

| File | Purpose |
| --- | --- |
| `app.py` | Streamlit user interface and prediction pipeline |
| `model.h5` | Trained TensorFlow/Keras ANN model |
| `onehot_encoder_geo.pkl` | Fitted encoder for `Geography` |
| `label_encoder_gender.pkl` | Fitted encoder for `Gender` |
| `scaler.pkl` | Fitted feature scaler |

The encoders and scaler must match the feature order and preprocessing used when training `model.h5`.

## Input fields

The interface collects:

- Geography and gender
- Credit score, age, balance, tenure, and estimated salary
- Number of products
- Credit card ownership
- Active member status

The app reports the customer as likely to churn when the model probability is greater than `0.5`.

## Project structure

- `Churn_Modelling.csv`: source dataset
- `experiment.ipynb`: model experimentation and training notebook
- `predict.ipynb`: prediction workflow notebook
- `logs/`: TensorBoard training logs
- `app.py`: deployable Streamlit application

## View training logs

To inspect TensorBoard logs, run:

```powershell
tensorboard --logdir logs
```
