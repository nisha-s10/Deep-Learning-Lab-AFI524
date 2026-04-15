# 🧪 Experiment 8: Autoencoders and Variational Autoencoders (VAE) with Latent Space Analysis and Model Comparison

---

## 📌 Objective

The objective of this experiment is to implement and analyze **Autoencoders** and **Variational Autoencoders (VAE)** using the **Fashion-MNIST** dataset.

This experiment focuses on:

* Learning meaningful latent representations
* Comparing deterministic and probabilistic models
* Evaluating reconstruction and generation performance
* Studying the effect of latent dimensions, loss functions, and optimizers
* Visualizing latent space structure and smooth transitions

Autoencoders learn deterministic compressed representations, whereas Variational Autoencoders learn probabilistic latent distributions enabling smooth data generation.

---

## 📂 Dataset

**Fashion-MNIST**

The dataset contains grayscale images of clothing items such as:

* 👕 Shirts
* 👚 T-shirts
* 👟 Shoes
* 👜 Bags
* 👡 Sandals
* 👗 Dresses

### Dataset Details

* Image Size: **28 × 28 pixels**
* Format: **Grayscale**
* Total Samples: **70,000**

### Dataset Split

* **80% Training**
* **10% Validation**
* **10% Testing**

---

## ⚙️ Preprocessing

The following preprocessing steps were applied:

* Normalization of pixel values to **[0, 1]**
* Flattening images to **784-dimensional vectors**
* Batch loading using PyTorch DataLoader

---

## 🏗️ Model Architectures

---

### 1️⃣ Autoencoder

The Autoencoder consists of two main components:

#### Encoder

* Fully connected neural network layers
* Maps input image to latent vector

#### Decoder

* Mirrors the encoder architecture
* Reconstructs image from latent vector

#### Loss Functions Used

* Mean Squared Error (**MSE**)
* Binary Cross Entropy (**BCE**)

---

### 2️⃣ Variational Autoencoder (VAE)

The Variational Autoencoder extends the Autoencoder by learning a **probabilistic latent distribution**.

#### Key Components

* Mean (**μ**) and variance (**σ**) estimation
* Reparameterization trick
* KL Divergence regularization

#### Reparameterization Equation

```
z = μ + σ · ε
ε ~ N(0,1)
```

#### Loss Function

```
Total Loss = Reconstruction Loss + KL Divergence
```

---

## 🧪 Experiments Performed

---

### 1️⃣ Latent Space Study

Models were trained using different latent dimensions:

* **2**
* **8**
* **16**
* **32**

Analysis included:

* Reconstruction quality
* Latent space structure
* Performance comparison

---

### 2️⃣ Latent Space Visualization

The latent space was visualized using:

* 2D scatter plots
* Cluster analysis
* Category separation

This helped evaluate how well the models learned meaningful representations.

---

### 3️⃣ Latent Space Interpolation

Interpolation was performed between two latent vectors:

```
z_interp = (1 − α)z₁ + αz₂
```

This demonstrated:

* Smooth transitions between clothing categories
* Continuity of the latent space
* Generative capability of the VAE

---

### 4️⃣ Loss Function Comparison

The following loss functions were evaluated:

* Binary Cross Entropy (**BCE**)
* Mean Squared Error (**MSE**)

Comparison metrics:

* Reconstruction accuracy
* Image sharpness
* Training behavior

---

### 5️⃣ Optimizer Comparison

The models were trained using:

* **SGD**
* **RMSprop**
* **Adam**

Comparison metrics:

* Convergence speed
* Training stability
* Loss reduction

---

### 6️⃣ Model Evaluation

Models were evaluated based on:

* Reconstruction quality
* Latent space smoothness
* Generation capability
* Interpolation performance
* Training stability

---

## 📊 Key Observations

* Autoencoder produced sharper reconstructions
* VAE generated smoother transitions between images
* Increasing latent dimension improved reconstruction quality
* Adam optimizer provided the most stable training
* VAE learned a structured and continuous latent space

---

## 🎯 Expected Outcomes Achieved

* Better reconstruction sharpness in Autoencoder
* Better generative capability and smoother transitions in VAE
* Meaningful latent space representation for Fashion-MNIST data
* Understanding of probabilistic generative models
* Experience with experiment tracking and model deployment

---

## 🛠️ Technologies Used

* Python
* PyTorch
* NumPy
* Matplotlib
* Scikit-learn
* Weights & Biases
* Hugging Face
* Google Colab

---

## 📁 Repository Structure

```
experiment-8/
│
├── experiment-8.ipynb
├── README.md
│
├── models/
│   ├── autoencoder_latent2.pth
│   ├── autoencoder_latent8.pth
│   ├── autoencoder_latent16.pth
│   ├── autoencoder_latent32.pth
│   ├── vae_latent2.pth
│   ├── vae_latent8.pth
│   ├── vae_latent16.pth
│   └── vae_latent32.pth
│
├── plots/
│   ├── reconstruction_comparison.png
│   ├── latent_space_visualization.png
│   ├── optimizer_comparison.png
│   └── loss_function_comparison.png
```

---

## ▶️ How to Run the Experiment

### Step 1 — Clone the Repository

```
git clone https://github.com/your-username/experiment-8.git
```

### Step 2 — Install Dependencies

```
pip install torch torchvision matplotlib numpy wandb huggingface_hub
```

### Step 3 — Run the Notebook

```
Open experiment-8.ipynb  
Run all cells
```

---

## 🔗 Submission Links

### GitHub Repository

```
Add your GitHub repository link here
```

### Weights & Biases Dashboard

```
Add your W&B project link here
```

### Hugging Face Model Repository

```
Add your Hugging Face model link here
```

---

## 🏁 Conclusion

The implementation of **Autoencoder** and **Variational Autoencoder (VAE)** successfully demonstrated the ability to learn meaningful latent representations from the Fashion-MNIST dataset.

Key findings include:

* Autoencoder achieved strong reconstruction performance
* VAE provided smoother latent space transitions and generative capability
* Adam optimizer showed stable and efficient convergence
* Latent dimension significantly affected reconstruction quality

This experiment highlights the importance of probabilistic modeling and structured latent representations in modern deep learning systems.

---

## 👩‍💻 Author

Nisha Singh  
M.Tech AI / Deep Learning Lab
