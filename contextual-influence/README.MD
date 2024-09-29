# Temporal Relationship Validity Prediction Model

## Overview

This project implements a model that predicts the validity of temporal relationships between events in sentences. Using **DistilBERT**, a lightweight variant of BERT, the model classifies whether a specified temporal relationship is valid (1) or invalid (0).

## Objectives

- **Contextual Understanding**: Analyze a sentence to determine the validity of temporal relationships between events.
- **Binary Classification**: Output a binary label indicating the validity of the temporal relationship:
  - **1**: Valid
  - **0**: Invalid
- **Utilization of DistilBERT**: Leverage the power of a pre-trained language model to understand the nuances in natural language.

## Installation

To set up the project, ensure you have Python 3.x installed, and then install the necessary packages:

```bash
pip install torch torchvision torchaudio transformers pandas scikit-learn

## Dataset

The model uses a dataset named `MATRES.csv`, which should be placed in the root directory of the project. This dataset contains sentences with temporal markers and corresponding validity labels.

### Dataset Structure

- **bodytext**: The main text of the sentence.
- **after**: Indicates if the event happens after a specified time (yes/no).
- **before**: Indicates if the event happens before a specified time (yes/no).
- **verb**: The action word in the sentence.
- **label**: Binary label for the validity of the temporal relationship (1 for valid, 0 for invalid).

## Model Architecture

The model consists of the following components:

- **DistilBERT**: For embedding the sentence context.
- **Linear Layer**: For binary classification of the temporal relationship.
- **Dropout Layer**: To prevent overfitting.
