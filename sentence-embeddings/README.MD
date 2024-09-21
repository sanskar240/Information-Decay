# Temporal Relevance Assessment Using Sentence Embeddings

## Problem Statement
Determine the temporal relevance of sentences based on their semantic meaning using an LSTM model.

## Inputs

1. **Sentence Embeddings**:
   - **Description**: A matrix of sentence embeddings representing the input sentences, capturing their semantic meaning.
   - **Shape**: `(batch_size, embedding_dim)`
   - **Example**: 
     ```python
     [
       [0.1, 0.2, 0.3],  # Sentence 1 embedding
       [0.4, 0.5, 0.6],  # Sentence 2 embedding
       [0.7, 0.8, 0.9]   # Sentence 3 embedding
     ]
     ```

2. **Temporal Indicators** (Optional):
   - **Description**: Additional features indicating temporal relationships (e.g., keywords like "before," "after").
   - **Shape**: `(batch_size, num_temporal_indicators)`
   - **Example**:
     ```python
     [
       [1, 0],  # Sentence 1 has "before"
       [0, 1],  # Sentence 2 has "after"
       [0, 0]   # Sentence 3 has no temporal indicators
     ]
     ```

3. **Contextual Features** (Optional):
   - **Description**: Additional contextual information related to the sentences that may aid in evaluating temporal relevance.
   - **Shape**: This can vary based on features included.
   - **Example**:
     ```python
     [
       [2],  # Sentence 1 context feature
       [1],  # Sentence 2 context feature
       [3]   # Sentence 3 context feature
     ]
     ```

## Outputs

1. **Relevance Scores**:
   - **Description**: A score indicating the temporal relevance of each sentence to a given context or event.
   - **Shape**: `(batch_size, 1)`
   - **Example**:
     ```python
     [
       [0.8],  # Sentence 1 relevance score
       [0.4],  # Sentence 2 relevance score
       [0.7]   # Sentence 3 relevance score
     ]
     ```

2. **Classification Labels** (if using a classification approach):
   - **Description**: Labels indicating whether the sentence is relevant or not based on temporal context.
   - **Shape**: `(batch_size, 1)`
   - **Example**:
     ```python
     [
       [1],  # Sentence 1 is relevant
       [0],  # Sentence 2 is not relevant
       [1]   # Sentence 3 is relevant
     ]
     ```

## Example Workflow

1. **Input Sentences**:
   - Sentence 1: "The meeting was scheduled before the presentation."
   - Sentence 2: "We will discuss the report after lunch."
   - Sentence 3: "The weather was nice."

2. **Generate Sentence Embeddings**:
   - Obtain embeddings for each sentence using a pre-trained model (e.g., BERT).

3. **Prepare Input Data**:
   - Formulate the input for the LSTM as:
     - **Sentence Embeddings**: 
       ```python
       [
         [0.1, 0.2, 0.3], 
         [0.4, 0.5, 0.6], 
         [0.7, 0.8, 0.9]
       ]
       ```
     - **Temporal Indicators**: 
       ```python
       [
         [1, 0], 
         [0, 1], 
         [0, 0]
       ]
       ```

4. **Model Training**:
   - Train the LSTM model on the input data, learning to predict relevance scores or classifications.

5. **Output Results**:
   - After training, input new sentences to get relevance scores and classifications.





