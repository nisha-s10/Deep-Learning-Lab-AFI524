# Sentiment Analysis using Simple RNN

## Project Overview

This project implements a **Sentiment Analysis classifier** for movie reviews using a **Simple Recurrent Neural Network (SimpleRNN)**.  

The goal is to classify reviews as **positive or negative** using the **IMDB Movie Reviews dataset**.  

Two models are implemented and compared:

- **Baseline SimpleRNN**
- **Improved SimpleRNN with regularization and bidirectional processing**

---

# Dataset

The **IMDB Movie Reviews dataset** is used for this experiment.

- Total reviews: **50,000**
- Binary sentiment classification (**Positive / Negative**)

Dataset split:

| Dataset | Size |
|------|------|
| Training | 20,000 |
| Validation | 5,000 |
| Test | 25,000 |

The dataset is available directly through **TensorFlow/Keras datasets**.

---

# Data Preprocessing

The following preprocessing steps were applied before training:

### 1. Lowercasing
The IMDB dataset provided by Keras is already lowercased and preprocessed.

### 2. Tokenization
Reviews are converted into sequences of integers representing words.

### 3. Vocabulary Size Limitation
Only the **20,000 most frequent words** were kept.
`Vocabulary Size: 20,000`

### 4. Padding and Truncation

All sequences are padded or truncated to a fixed length.
`Max Sequence Length: 250`


### Example

Raw review:
`i think this could've been a decent movie and some of its parts are ok ...`


Processed sequence:
`[11, 13, 104, 14, 2856, 77, 6, 542, 20, 5, 49, 7, 94, 531, ...]`


---

# Model Architectures

## 1. Baseline SimpleRNN

`The baseline model consists of three layers:
Embedding(vocab_size, embedding_dim), SimpleRNN(hidden_units), Dense(1, activation="sigmoid")`


Training configuration:

- Loss: **Binary Crossentropy**
- Optimizer: **Adam**
- Metrics: **Accuracy, AUC**
- Batch Size: **64**
- Epochs: **10**
- EarlyStopping: **Patience = 2**

---

## 2. Improved SimpleRNN

To improve performance, several enhancements were added.

### Improvements Used

1. **SpatialDropout1D**
   - Reduces overfitting by dropping embedding channels.

2. **Bidirectional SimpleRNN**
   - Processes sequences in both forward and backward directions.

3. **Dropout**
   - Prevents overfitting during training.

Improved architecture:

`Embedding(vocab_size, embedding_dim), SpatialDropout1D, Bidirectional(SimpleRNN(hidden_units)), Dropout, Dense(1, activation="sigmoid")`


---

# Training Results

## Baseline Model Behavior

The baseline model shows:

- Increasing **training accuracy**
- Nearly constant **validation accuracy (~50%)**

This indicates **overfitting**, where the model memorizes training data but fails to generalize.

### Baseline Training Curves

![Baseline Accuracy and Loss](baseline_accuracy.png, baseline_loss.png)

---

## Improved Model Behavior

The improved model demonstrates:

- Higher validation accuracy
- Better generalization

This improvement is due to **bidirectional context learning and regularization techniques**.

---

# Results Comparison

| Model | Accuracy | Precision | Recall | F1-score |
|------|------|------|------|------|
| Baseline SimpleRNN | 0.66 | - | - | - |
| Improved SimpleRNN | 0.86 | 0.76 | 0.76 | 0.76 |

The improved model significantly outperforms the baseline model.

---

# Confusion Matrix

The confusion matrix visualizes prediction performance on the test dataset.

![Confusion Matrix](images/confusion_matrix.png)

---

# Error Analysis

Misclassified examples were analyzed to understand model limitations.

### Example 1

Review snippet:
`The movie had great actors but the story was extremely boring.`


True label: **Positive**  
Predicted probability: **0.32**

Reason:

The review contains mixed sentiment words such as *great actors* and *boring*, which confused the model.

---

### Example 2

Review snippet:
`I expected a lot from this movie but it turned out to be disappointing.`


True label: **Negative**  
Predicted probability: **0.61**

Reason:

The model incorrectly focused on neutral words rather than the negative sentiment.

---

# Analysis Questions

### Why do Simple RNNs struggle with long sequences?

Simple RNNs suffer from the **vanishing gradient problem**, which limits their ability to remember long-term dependencies. LSTMs and GRUs solve this problem using gating mechanisms.

---

### What does padding/truncation affect?

Padding ensures fixed-length sequences for batch processing. However, truncation may remove important context from long reviews.

---

### Why might training accuracy be high but validation accuracy low?

This indicates **overfitting**, where the model memorizes training data but cannot generalize to unseen examples.

---

### Which improvement helped most?

The **Bidirectional SimpleRNN** helped the most because it allows the model to analyze sequences in both directions, improving context understanding.

---

# Conclusion

This project demonstrates sentiment classification using Simple RNN architectures.

Key findings:

- Baseline SimpleRNN struggles with generalization.
- Regularization techniques and bidirectional processing significantly improve performance.
- The improved model achieves **~80% accuracy on the IMDB dataset**.

This highlights the importance of architectural improvements and regularization in deep learning models for NLP tasks.

---

# Technologies Used

- Python
- TensorFlow / Keras
- NumPy
- Matplotlib
- Scikit-learn
