# Forest Fire Area Prediction

This repository contains a machine learning model for predicting forest fire areas using a dataset with various meteorological and environmental features. The project is implemented in Python using TensorFlow and Keras.

## Dataset

The dataset contains the following features:

- **X, Y**: Spatial coordinates within the Montesinho park map: 1 to 9.
- **month**: Month of the year: 'jan' to 'dec'.
- **day**: Day of the week: 'mon' to 'sun'.
- **FFMC**: Fine Fuel Moisture Code index from the FWI system: 18.7 to 96.20.
- **DMC**: Duff Moisture Code index from the FWI system: 1.1 to 291.3.
- **DC**: Drought Code index from the FWI system: 7.9 to 860.6.
- **ISI**: Initial Spread Index from the FWI system: 0.0 to 56.10.
- **temp**: Temperature in Celsius degrees: 2.2 to 33.30.
- **RH**: Relative humidity in %: 15.0 to 100.
- **wind**: Wind speed in km/h: 0.40 to 9.40.
- **rain**: Outside rain in mm/m2: 0.0 to 6.4.
- **area**: The burned area of the forest (in ha): 0.00 to 1090.84.

## Data Preprocessing

1. **Mapping Categorical Features**:
   - The `month` feature is mapped from month names to numerical values.
   - The `day` feature is mapped from day names to numerical values.

2. **Handling Duplicates**:
   - Duplicate records are identified and removed to ensure the dataset's integrity.

3. **Train-Test Split**:
   - The dataset is split into a training set (70%) and a test set (30%).

4. **Feature Scaling**:
   - Selected features (`FFMC`, `DMC`, `DC`) are scaled using TensorFlow's `Normalization` layer to standardize the input data.

## Model

A simple neural network model is built using TensorFlow and Keras:

1. **Normalization Layer**:
   - Normalizes the input features to have zero mean and unit variance.

2. **Dense Layer**:
   - A single dense layer with one unit to predict the target variable `area`.

## Training

- The model is compiled with the Adam optimizer and Mean Absolute Error (MAE) loss function.
- The model is trained for 100 epochs with a validation split of 20%.

## Evaluation

- The model's performance is evaluated on the test set using the same loss function (MAE).

## Visualizations

- A custom plotting function is defined to visualize the relationship between individual features and the target variable `area`.

## Instructions

To run the project:

1. Ensure you have the necessary dependencies installed (TensorFlow, Keras, pandas, numpy, matplotlib).
2. Load the dataset and follow the data preprocessing steps.
3. Define and compile the model.
4. Train the model on the training set.
5. Evaluate the model on the test set.
6. Use the provided plotting function to visualize predictions.

## Notes

- Ensure to adapt the normalization layer to the training data before using it to transform the features.
- Monitor the training and validation loss to check for overfitting or underfitting during model training.

This project demonstrates a basic workflow for building and evaluating a machine learning model for regression tasks, specifically predicting the burned area of forest fires based on various environmental and meteorological features.
