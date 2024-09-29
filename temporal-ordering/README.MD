# Temporal Event Ordering with LSTM

## Overview
This project implements a temporal event ordering model using LSTM to classify and order events based on their temporal relationships. The model processes sentences with temporal markers and predicts the correct order of events, enhancing understanding in natural language processing (NLP) tasks related to temporal reasoning.

## Features
- **Data Parsing**: Extracts events, T-LINKs, and TIMEX3 entities from TimeML formatted XML files.
- **Tokenization**: Utilizes a custom tokenizer to convert text into sequences for the LSTM model.
- **LSTM Model**: A bidirectional LSTM architecture to classify the temporal relationships between events.
- **Evaluation Metrics**: Implements accuracy, precision, recall, and F1 score metrics to evaluate model performance.

## Installation
To run this project, ensure you have Python 3.7+ installed along with the necessary libraries. You can install the required libraries using pip:

```bash
pip install pandas torch numpy scikit-learn
