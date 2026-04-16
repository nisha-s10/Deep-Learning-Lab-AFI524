# 🧪 Experiment 10: Image Classification using Vision Transformers (ViT) with Augmentation and Model Comparison

---

## 📌 Objective

The objective of this experiment is to implement an image classification system using the **Vision Transformer (ViT)** architecture and compare its performance with a **Convolutional Neural Network (ResNet-18)**.

Unlike Convolutional Neural Networks (CNNs), which rely on convolution operations, **Vision Transformers** process images as sequences of patches and use **self-attention mechanisms** to learn global relationships between image regions.

This experiment aims to study:

* The effect of **data augmentation**
* The impact of different **loss functions**
* The influence of different **optimizers**
* Performance comparison between **transformer-based** and **CNN-based** models

---

## 📂 Dataset

**CIFAR-10 Dataset**

The dataset contains 60,000 color images across 10 classes:

* ✈️ Airplane
* 🚗 Automobile
* 🐦 Bird
* 🐱 Cat
* 🦌 Deer
* 🐶 Dog
* 🐸 Frog
* 🐴 Horse
* 🚢 Ship
* 🚚 Truck

### Dataset Details

* Image size: **32 × 32 pixels**
* Channels: **RGB**
* Total samples: **60,000**

### Dataset Split

* **80% Training**
* **10% Validation**
* **10% Testing**

---

## ⚙️ Preprocessing and Augmentation

The following preprocessing steps were applied:

* Image resizing to **224 × 224**
* Pixel normalization
* Tensor conversion

### Data Augmentation

Two dataset versions were created:

**Original Dataset**

* Normalization
* Resizing

**Augmented Dataset**

* Horizontal Flip
* Vertical Flip
* Normalization
* Resizing

Models were trained on:

* Original dataset
* Augmented dataset

---

## 🏗️ Model Architectures

---

# 1️⃣ Vision Transformer (ViT)

The Vision Transformer treats an image as a sequence of patches and applies transformer-based attention mechanisms.

### Components Implemented

* Patch Embedding
* Positional Encoding
* Transformer Encoder
* Classification Token (CLS Token)
* Classification Head

### Workflow

```text
Image → Patches → Embedding → Transformer Encoder → Classification
```

---

## Patch Embedding

Images are divided into fixed-size patches:

```text
224 × 224 image
Patch size = 16 × 16
```

These patches are flattened and projected into embedding vectors.

---

## Positional Encoding

Positional encodings were added to patch embeddings to preserve spatial information.

---

## Transformer Encoder

The encoder consists of:

* Multi-head self-attention
* Feed-forward neural network
* Residual connections
* Layer normalization

Multiple encoder layers were stacked to learn hierarchical representations.

---

## Classification Token (CLS Token)

A learnable **CLS token** was introduced and used for final classification.

---

# 2️⃣ CNN Baseline — ResNet-18

A **ResNet-18** model was implemented as the CNN baseline.

### Key Features

* Convolutional layers
* Residual connections
* Batch normalization
* Fully connected classification head

Both ViT and ResNet-18 used identical preprocessing and augmentation to ensure fair comparison.

---

# 3️⃣ Loss Functions

Models were trained using the following loss functions:

* Cross-Entropy Loss
* Label Smoothing Loss
* Focal Loss

### Purpose

* Cross-Entropy: Standard classification loss
* Label Smoothing: Reduces overconfidence
* Focal Loss: Focuses on hard examples

---

# 4️⃣ Optimizers

Models were trained using:

* **SGD**
* **RMSprop**
* **Adam**

### Comparison Criteria

* Convergence speed
* Stability
* Generalization performance

---

# 5️⃣ Training and Experiment Tracking

All experiments were tracked using **Weights & Biases**.

### Metrics Logged

* Training loss
* Validation loss
* Training accuracy
* Validation accuracy
* Training time

This enabled monitoring of:

* Model convergence
* Training stability
* Performance trends

---

# 6️⃣ Model Logging and Deployment

Trained models were saved and prepared for deployment.

### Platforms Used

* Weights & Biases
* Hugging Face
* GitHub

### Saved Models

* Vision Transformer model
* ResNet-18 model

---

# 7️⃣ Evaluation

Models were evaluated using the following criteria:

## Performance Metrics

* Test accuracy
* Training time
* Model complexity

---

## Comparisons Performed

* Vision Transformer vs ResNet-18
* Original dataset vs Augmented dataset
* Different loss functions
* Different optimizers

---

# 8️⃣ Analysis and Discussion

---

## Effect of Data Augmentation

Observations:

* Horizontal and vertical flips increased dataset diversity
* Augmentation improved model generalization
* Overfitting was reduced

---

## Vision Transformer vs ResNet-18

Key insights:

* ResNet-18 performed well on smaller datasets
* ViT captured global image relationships
* CNN inductive bias helped in early convergence
* ViT showed strong scalability

---

## Loss Function Comparison

### Cross-Entropy

* Stable training
* Reliable baseline

### Label Smoothing

* Reduced overconfidence
* Improved generalization

### Focal Loss

* Improved performance on difficult samples
* Reduced class imbalance impact

---

## Optimizer Comparison

### SGD

* Slower convergence
* Less stable

### RMSprop

* Moderate performance
* Faster than SGD

### Adam

* Fastest convergence
* Most stable training

---

# 9️⃣ Observations

Key observations during training:

* Training loss decreased steadily across epochs
* Validation accuracy improved with augmentation
* Adam optimizer provided stable convergence
* ViT required more computation time than ResNet-18
* Augmented data improved model performance

---

# 🎯 Expected Outcomes Achieved

* Improved performance with data augmentation
* Clear understanding of transformer vs CNN behavior
* Insight into optimizer and loss function impact
* Experience with experiment tracking and model deployment

---

# 🛠️ Technologies Used

* Python
* PyTorch
* Torchvision
* Vision Transformer (ViT)
* ResNet-18
* NumPy
* Matplotlib
* Weights & Biases
* Hugging Face
* Google Colab / Kaggle

---

# 📁 Repository Structure

```text
experiment-10/
│
├── experiment-10.ipynb
├── README.md
│
├── models/
│   ├── vit_model.pth
│   ├── resnet18_model.pth
│
├── plots/
│   ├── training_loss_curve.png
│   ├── validation_accuracy.png
│   ├── model_comparison.png
```

---

# ▶️ How to Run the Experiment

## Step 1 — Clone the Repository

```bash
git clone https://github.com/your-username/experiment-10.git
```

---

## Step 2 — Install Dependencies

```bash
pip install torch torchvision timm wandb huggingface_hub
```

---

## Step 3 — Run the Notebook

```text
Open experiment-10.ipynb
Run all cells
```

---

# 🔗 Submission Links

## GitHub Repository

```
Add your GitHub repository link here
```

## Weights & Biases Dashboard

```
Add your W&B project link here
```

## Hugging Face Model Repository

```
Add your Hugging Face model link here
```

---

# 🏁 Conclusion

The Vision Transformer and ResNet-18 models were successfully implemented and compared for image classification on the CIFAR-10 dataset.

Key conclusions:

* Data augmentation improved model performance
* ResNet-18 converged faster on small datasets
* Vision Transformers captured global relationships effectively
* Adam optimizer provided the most stable training

This experiment demonstrated the practical differences between transformer-based and convolution-based architectures in image classification.

---

## 👩‍💻 Author

Nisha Singh  
M.Tech AI / Deep Learning Lab
