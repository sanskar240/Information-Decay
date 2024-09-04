# Tempo-Ordering

Key Achievements of the First Event Sequencing Model

Event Pair Generation:

We successfully generated pairs of events from the TimeBank and TimeEval-3 datasets.

Each pair of events is labeled with a binary value:

1 if the first event occurs before the second.
0 if the second event occurs before the first.

Robust Data Handling:

We introduced error handling to manage missing event pairs. If an event pair is incomplete (i.e., one or both events are missing from the dataset), we skip the pair and log the issue. This prevents the model from crashing due to missing data and allows us to diagnose potential issues in the dataset.

Tokenization and Padding:

We tokenized the event text, converting words into numerical sequences that the LSTM model can process.
We padded these sequences to ensure that all inputs to the model have the same length, which is crucial for training LSTM models.

Data Preparation for Model Training:

We split the data into training and testing sets, which allows us to train the model on one portion of the data and evaluate its performance on another portion.
The resulting data (X1_train, X2_train, y_train, etc.) is ready to be fed into a neural network model, specifically a Siamese LSTM architecture, where each pair of events will be compared to predict their temporal relationship.
