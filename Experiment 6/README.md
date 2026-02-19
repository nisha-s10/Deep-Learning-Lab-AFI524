# 🧪 Experiment 6  
# Encoder–Decoder Architecture with Bahdanau & Luong Attention

---

## 📌 Objective

The objective of this experiment is to implement a complete Sequence-to-Sequence (Seq2Seq) architecture for machine translation using:

- Vanilla LSTM Encoder–Decoder  
- Bahdanau (Additive) Attention  
- Luong (Multiplicative) Attention  

The performance of all three models is compared using BLEU score evaluation and attention visualization.

---

## 📂 Dataset

The dataset consists of English–Spanish sentence pairs in tab-separated format:

Hello. Hola.
How are you? ¿Cómo estás?


### Data Split
- 80% Training  
- 10% Validation  
- 10% Testing  

---

## ⚙️ Implementation Steps

### 1️⃣ Data Preprocessing
- Lowercasing
- Removing special characters
- Tokenization
- Vocabulary creation
- Special tokens:
  - `<pad>`
  - `<sos>`
  - `<eos>`
  - `<unk>`

---

### 2️⃣ Dataset Preparation
- Sequence encoding
- Padding to fixed `MAX_LEN`
- DataLoader with batching

---

### 3️⃣ Model Architectures

#### 🔹 Vanilla Encoder–Decoder
- LSTM Encoder
- LSTM Decoder
- Teacher Forcing

#### 🔹 Bahdanau Attention
Additive attention mechanism:

score = vᵀ tanh(W₁hᵢ + W₂sₜ)

#### 🔹 Luong Attention
Multiplicative attention mechanism:

score = hₜᵀ W hₛ

---

### 4️⃣ Training
- Optimizer: Adam  
- Loss Function: CrossEntropyLoss (ignoring `<pad>`)  
- Teacher Forcing Ratio: 0.5  
- Multiple epochs  

---

### 5️⃣ Evaluation

Evaluation Metric:

- **BLEU Score**

Each model is evaluated on the test dataset.

---

### 6️⃣ Attention Visualization

Attention weights are visualized using heatmaps to show:

- Alignment between source and target tokens  
- Decoder focus during translation  

---

## 📊 Results Comparison

| Model | BLEU Score | Performance |
|-------|------------|-------------|
| Vanilla LSTM | Lower | Struggles with long dependencies |
| Bahdanau Attention | Higher | Better alignment |
| Luong Attention | Comparable / Slightly better | Efficient attention scoring |

---

## 🧠 Key Observations

- Attention improves translation quality significantly.
- Vanilla Seq2Seq struggles due to fixed context vector.
- Bahdanau attention improves alignment quality.
- Luong attention is computationally efficient.

---

## 🚀 Technologies Used

- Python
- PyTorch
- NumPy
- NLTK
- Matplotlib
- Seaborn
- Scikit-learn

---
## 📁 Project Structure

```
Experiment6/
│
├── spa.txt
├── experiment6.ipynb
├── README.md
```


---

## ▶️ How to Run

1. Install dependencies:

pip install torch nltk seaborn matplotlib scikit-learn


2. Place `eng_spa.txt` inside the project folder.

3. Run the notebook or Python script.

---

## 🎯 Conclusion

This experiment demonstrates how attention mechanisms enhance sequence-to-sequence models by allowing the decoder to dynamically focus on relevant encoder outputs. Both Bahdanau and Luong attention improve BLEU scores compared to the vanilla encoder–decoder model.

---

## 👩‍💻 Author

Machine Learning Lab – Experiment 6  
Sequence-to-Sequence Learning with Attention


