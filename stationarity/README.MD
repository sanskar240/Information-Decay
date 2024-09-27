# Temporal Event Classification Model

## Overview

This project aims to classify temporal events based on their descriptions into two categories: **Stationarity** and **Non-Stationarity**. We utilize a deep learning approach with an LSTM model and leverage the DistilBERT model for text embeddings. The model is designed to predict whether a given event is stationary (occurring at regular intervals) or non-stationary (occurring irregularly or only once).

The dataset used for training the model is sourced from `mc-taco.tsv`, which contains event descriptions and their corresponding classifications. The project demonstrates how to preprocess the data, convert text to embeddings, train a model, and evaluate its performance.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Implementation Details](#implementation-details)
- [Results](#results)
- [License](#license)

## Installation

To run this project, ensure you have Python installed (version 3.6 or later is recommended). It is recommended to create a virtual environment to manage dependencies:

1. **Create a Virtual Environment** (optional but recommended):

   ```bash
   python -m venv venv


## Implementation Details

### 1. Data Preparation
- The dataset is loaded from a TSV file and cleaned by stripping whitespace from column names and renaming them for easier access.
- The target variable `Stationarity` is mapped to binary values: `1` for Stationarity and `0` for various types of Non-Stationarity.
- Any rows with NaN values in the target column are removed.

### 2. Tokenization and Embedding
- We use the DistilBERT model for obtaining embeddings of event descriptions.
- Each event description is tokenized and converted into a vector representation using the DistilBERT tokenizer and model.

### 3. Splitting the Dataset
- The dataset is split into training and testing sets using a stratified split to maintain the distribution of the target variable.

### 4. Model Definition
- An LSTM model is defined with the following components:
  - LSTM layer for sequence modeling.
  - Fully connected layer to map the LSTM output to the desired output size (1 for binary classification).
  - Sigmoid activation function to produce probabilities.

### 5. Training the Model
- The model is trained using binary cross-entropy loss and the Adam optimizer.
- A training loop iterates through a specified number of epochs, updating the model weights based on the loss calculated from the predictions.

### 6. Evaluation
- The model is evaluated on the test set, and accuracy is calculated.
- A classification report is generated to provide detailed metrics on model performance.

### 7. Prediction Function
- A function is provided to make predictions on new sentences. The function converts the input sentences into DistilBERT embeddings and uses the trained model to predict stationarity.

### 8. Example Predictions
- The script includes example inputs to demonstrate the model's predictions on new event descriptions.

## Results

After training the model, the classification report provides insights into the model's performance, including precision, recall, and F1 score for both classes.

### Example Outputs
- When predicting on example sentences, the output shows whether each sentence is classified as Stationarity (1) or Not Stationarity (0).
