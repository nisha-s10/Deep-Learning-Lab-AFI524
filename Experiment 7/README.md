# 🧪 Experiment 7: Transformer-Based Encoder-Decoder for English-to-Spanish Translation

## 📌 Objective

To implement a complete Transformer-based Encoder-Decoder model from scratch for English-to-Spanish translation and compare its performance with LSTM-based Seq2Seq models.

---

## 📂 Dataset

- Dataset: `spa.txt`
- Contains English–Spanish sentence pairs.
- Preprocessed using:
  - Lowercasing
  - Special character cleaning
  - Tokenization
- Split into:
  - 80% Training
  - 10% Validation
  - 10% Testing

---

## 🏗️ Model Architecture

The Transformer model was implemented manually (without using `nn.Transformer`) and includes:

### 1️⃣ Embedding Layer
- Learned embeddings for both source (English) and target (Spanish).

### 2️⃣ Positional Encoding
- Sinusoidal positional encoding.
- Added to embeddings to retain word order information.

### 3️⃣ Scaled Dot-Product Attention
\[
Attention(Q,K,V) = softmax\left(\frac{QK^T}{\sqrt{d_k}}\right)V
\]

### 4️⃣ Multi-Head Attention
- Multiple attention heads
- Linear projections for Q, K, V
- Concatenation and final projection

### 5️⃣ Transformer Encoder
Each encoder layer includes:
- Multi-head self-attention
- Feed Forward Network
- Residual connections
- Layer Normalization
- Stacked encoder layers

### 6️⃣ Transformer Decoder
Each decoder layer includes:
- Masked multi-head self-attention
- Encoder–Decoder (cross) attention
- Feed Forward Network
- Residual connections
- Layer Normalization
- Stacked decoder layers

### 7️⃣ Masking
- Padding mask for padded tokens
- Causal mask for decoder (prevents looking ahead)

---

## ⚙️ Training Details

- Optimizer: Adam
- Loss Function: CrossEntropyLoss (ignore padding index)
- Teacher Forcing: Implemented via shifted target input
- Batch Size: 32
- Epochs: 3–5 (adjustable)
- Reduced dataset size for Kaggle performance

---

## 📊 Evaluation Metrics

### 1️⃣ BLEU Score
Used to evaluate translation quality.

### 2️⃣ Training Loss
Loss curve plotted to observe convergence.

### 3️⃣ Training Time
Measured total training duration.

---

## 📈 Performance Comparison

| Model                  | BLEU Score | 
|------------------------|------------|
| Vanilla LSTM           | 0.0189     |
| Bahdanau Attention     | 0.0230     | 
| Luong Attention        | 0.0216     |
| Transformer            | 0.0347     |

> Transformer generally achieves higher BLEU due to parallel self-attention and better long-range dependency modeling.

---

## 🔎 Example Translation Outputs

Example:
`Source: stop moving.`
`Reference: deja de moverte.`
`Predicted: deja de moverte.`


The Transformer demonstrates contextual understanding and improved translation fluency compared to LSTM-based models.

---

## 🚀 Key Advantages of Transformer

- Parallel computation (faster training)
- Better long-range dependency modeling
- Multi-head attention captures diverse relationships
- State-of-the-art architecture for translation tasks

---

## 📁 Project Structure

```
Experiment7/
│
├── eng_spa.txt
├── experiment7.ipynb
├── README.md
```

---

## 🏁 Conclusion

The manually implemented Transformer-based Encoder-Decoder successfully performs English-to-Spanish translation. 

Compared to LSTM-based Seq2Seq models:
- Transformer achieved higher BLEU score
- Training was more parallelized
- Better contextual alignment was observed

This experiment demonstrates the effectiveness of attention-based architectures in sequence-to-sequence learning.

---

## 👩‍💻 Author

Nisha Singh  
M.Tech AI / Deep Learning Lab
