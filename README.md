# Airline-LSTM-Modeling

**OVERVIEW**

This project aims to forecast the number of international airline passengers using one of the most widely studied time-series datasets: the Monthly International Airline Passengers dataset (1949–1960). Using deep learning—specifically an LSTM-based neural network—the model learns long-term temporal patterns in the passenger data and predicts future monthly demand.
________________________________________
**DATASET**

Source: Monthly International Airline Passengers Dataset
URL: https://github.com/qusanskritibisht15/Airline-Forecasting/blob/main/airline-passengers.csv
Time Period: January 1949 – December 1960
Total Records: 144 monthly observations
This dataset is well-suited for sequence modelling because it shows clear seasonality, upward trends, and long-term growth in passenger numbers.
________________________________________
**LIBRARIES USED**

*	NumPy
*	Pandas
*	Matplotlib
*	Scikit-learn
*	TensorFlow / Keras
________________________________________
**APPROACH**

1. Data Exploration & Preprocessing
The dataset was loaded and examined to understand its overall structure, trends, and seasonality. The Passengers column was extracted as the main feature for forecasting. To stabilize training, values were scaled to the 0,1range using MinMaxScaler, ensuring the LSTM model handled the temporal patterns efficiently.
2. Sequence Generation
To train the LSTM model, the time series was converted into supervised learning sequences using a sliding-window technique:
	Input: 3 consecutive months
	Output: Passenger count of the following month
This approach helps the model learn short-term dependencies while still capturing long-term behavior.
3. LSTM Model Architecture
A simple but effective sequential model was built using:
	LSTM Layer: 50 units with ReLU activation
	Dense Output Layer: 1 neuron predicting the next month’s passenger count
This architecture balances accuracy and computational efficiency, making it ideal for a classical dataset.
4. Model Compilation
The model was compiled with:
	Optimizer: Adam
	Loss Function: Mean Squared Error (MSE)
	Evaluation Metric: Mean Absolute Error (MAE)
5. Training & Evaluation
The dataset was split into 80% training and 20% testing.
The model was trained for 200 epochs with a batch size of 8, allowing it to learn the underlying seasonality and growth trend.
Performance was assessed on unseen test data to ensure the model generalized well.
________________________________________
**VISUALIZATION**

Training and validation loss curves were plotted using Matplotlib, helping track the model’s learning progress and ensuring the model did not overfit.
________________________________________
**RESULTS**

	Test MSE: 0.0166
	Test MAE: 0.1052
	Forecasted Next-Month Passengers: ≈ 425.20
The LSTM model captured the dataset’s temporal structure effectively, producing a realistic and accurate forecast.
________________________________________
**CONCLUSION**

This project demonstrates how deep learning models—specifically LSTM networks—can extract and learn long-term seasonal patterns from time-series data. Even with a relatively simple architecture, the model produced strong predictive performance. This work forms a foundation for more advanced forecasting models, such as stacked LSTMs, GRUs, or hybrid statistical-ML approaches.
________________________________________
Author

Sanskriti Bisht
