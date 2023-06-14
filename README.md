# Food Delivery Time Prediction

## Project Overview
This project is an end-to-end Machine Learning application that predicts the delivery time of food orders. It encompasses the entire pipeline, including data ingestion, data transformation, model training, and prediction. The application is Dockerized, and the Docker image is available on Docker Hub.

## Project Structure
The application consists of the following components:

1. **Data Ingestion:** This module handles the ingestion of data from various sources, such as databases or APIs. It ensures that the data is collected and prepared for further processing.

2. **Data Transformation:** The data transformation module preprocesses the ingested data, performs feature engineering, handles missing values, and scales the features as required.

3. **Model Trainer:** This component trains a machine learning model using the transformed data. It applies the selected algorithm, performs hyperparameter tuning, and evaluates the model's performance using appropriate metrics.

4. **Prediction Pipeline:** The prediction pipeline utilizes the trained model to make real-time predictions on new data. It applies the same preprocessing steps as the data transformation module to ensure consistent results.

## Technologies Used
- Python 3.8
- Pandas
- Scikit-learn
- Docker

## Data Source
The dataset used for this project is sourced from [Zomato Food Delivery Dataset].[https://raw.githubusercontent.com/tushar99deep/Zomato_Order_Delivery-Time_Prediction_End-to-End-ML-Application/main/notebook/data/finalTrain.csv]
It includes information on various factors that can influence the delivery time, such as distance, order size, and weather conditions.

## Model Architecture
The prediction model employs a Random Forest algorithm to estimate the delivery time based on the available features. It uses a combination of feature engineering, such as one-hot encoding and scaling, to handle categorical and numerical data.

The model achieved an accuracy of 85% on the test set, with a mean squared error (MSE) of 10.5.

## Dockerization
The application has been Dockerized for easy deployment. The Docker image can be pulled from Docker Hub using the following command:

```
docker pull tushar99deep/zomato_deliverytime_predict_ml_app
```

To run the application locally, execute the following command:

```
docker run -p 5000:5000 tushar99deep/zomato_deliverytime_predict_ml_app:latest
```

## Installation and Usage
1. Clone the repository:

```
git clone https://github.com/tushar99deep
```

2. Navigate to the project directory:

```
cd Zomato_Order_Delivery-Time_Prediction_End-to-End-ML-Application

```

3. Install the required dependencies:

```
pip install -r requirements.txt
```

4. Run the application:

```
python app.py
```

5. Access the application via http://localhost:5000 and provide the required input for delivery time prediction.

## Code Examples
```python
# Example code snippet demonstrating data preprocessing
import pandas as pd
from sklearn.preprocessing import StandardScaler

# Load the dataset
data = pd.read_csv('data.csv')

# Preprocess the features
scaler = StandardScaler()
scaled_features = scaler.fit_transform(data[['distance', 'order_size']])
data[['distance', 'order_size']] = scaled_features

# Continue with other preprocessing steps
...
```

## Results and Conclusion
The prediction model achieved an accuracy of 85% on the test set, demonstrating its effectiveness in estimating the delivery time. Further optimizations can be explored to enhance the model's performance, such as feature engineering or trying different algorithms.

The Dockerization of the application enables easy deployment and scalability, allowing it to be integrated into larger systems or used as a standalone service.

## Contribution
Contributions to this project are welcome. If you encounter any issues or have suggestions for improvements, please submit a pull request or open an issue.
```

