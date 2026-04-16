# RNN-Bike-Demand-Prediction
A simple end-to-end Deep Learning project to predict next day bike demand using a stacked SimpleRNN model.

## Project Structure

```
RNN BIKE DEMAND/
│
├── data/                 # Dataset (bike.csv)
├── src/                 
│   ├── bike.ipynb        # Notebook 
│   └── models/           # Saved model & scalers
│       ├── model.h5
│       ├── x_scaler.pkl
│       └── y_scaler.pkl
│
├── main.py               # Main execution file
├── requirements.txt      # Dependencies
└── README.md             # Project documentation
```



**Workflow**
  Load dataset
  Convert date column & sort data
  Train-test split (no shuffle, time-based)
  Feature scaling using MinMaxScaler
  Create sequences (window = 7 days)
  Reshape data for RNN (samples, timesteps, features)
  Build stacked SimpleRNN model
  Train model
  Evaluate using RMSE
  Predict next day demand

 **Model Architecture**
 Input → SimpleRNN(64) → SimpleRNN(32) → Dense(1)

  First RNN → learns patterns
  Second RNN → refines patterns
  Dense → outputs final prediction
  
**How to Run**

1. Install dependencies
  pip install -r requirements.txt
2. Run training
  python main.py

**Evaluation Metric**
  RMSE (Root Mean Squared Error)
  Measures difference between actual and predicted values

**Prediction**
  Uses last 7 days data
  Applies scaling + reshaping
  Predicts next day bike demand

**Saved Files**
  model.h5 → trained RNN model
  x_scaler.pkl → feature scaler
  y_scaler.pkl → target scaler

**Key Concepts Used**
  Time Series Forecasting
  RNN (Recurrent Neural Network)
  Sequence Creation
  Feature Scaling
  Model Evaluation (RMSE)

  **Conclusion**
    This project demonstrates how to build a simple RNN-based time series model to predict bike demand using historical data.
