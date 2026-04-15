# Experiment 8: Autoencoders and Variational Autoencoders (VAE) with Latent Space Analysis and Model Comparison

## Overview

This experiment focuses on implementing and analyzing **Autoencoders** and **Variational Autoencoders (VAE)** using the **Fashion-MNIST** dataset.
The goal is to study latent representations, reconstruction performance, generative capability, and the effect of different configurations such as latent dimensions, loss functions, and optimizers.

Autoencoders learn deterministic compressed representations, whereas Variational Autoencoders learn probabilistic latent distributions that enable smooth data generation and interpolation.

---

## Objectives

The main objectives of this experiment are:

* Implement **Autoencoder** and **Variational Autoencoder (VAE)** architectures using PyTorch
* Learn meaningful latent representations of image data
* Compare deterministic and probabilistic generative models
* Analyze reconstruction quality and latent space structure
* Study the impact of:

  * Latent space dimensionality
  * Loss functions
  * Optimizers
* Perform latent space interpolation and visualization
* Track training and evaluation metrics
* Deploy trained models for reproducibility

---

## Dataset

**Fashion-MNIST**

The dataset consists of grayscale images of clothing items such as:

* Shirts
* T-shirts
* Shoes
* Bags
* Sandals
* Dresses

Each image is:

* Size: **28 × 28 pixels**
* Format: **Grayscale**
* Total samples: **70,000**

Dataset split:

* **80% Training**
* **10% Validation**
* **10% Testing**

---

## Preprocessing

The following preprocessing steps were applied:

* Normalization of pixel values to **[0, 1]**
* Flattening images to **784-dimensional vectors**
* Batch loading using PyTorch DataLoader

---

## Model Architectures

### Autoencoder

The Autoencoder consists of:

**Encoder:**

* Fully connected layers
* Maps input image to latent vector

**Decoder:**

* Mirrors encoder architecture
* Reconstructs image from latent vector

**Loss Functions Used:**

* Mean Squared Error (MSE)
* Binary Cross Entropy (BCE)

---

### Variational Autoencoder (VAE)

The VAE extends the Autoencoder by learning a probabilistic latent representation.

Key components:

* Mean (μ) and variance (σ) estimation
* Reparameterization trick
* KL Divergence regularization

**Reparameterization Equation:**

z = μ + σ · ε
ε ~ N(0,1)

**Loss Function:**

Total Loss = Reconstruction Loss + KL Divergence

---

## Experiments Performed

### 1. Latent Space Study

Models were trained with different latent dimensions:

* 2
* 8
* 16
* 32

Analysis included:

* Reconstruction quality
* Latent space structure
* Performance comparison

---

### 2. Latent Space Visualization

The latent space was visualized using:

* 2D scatter plots
* Cluster analysis
* Category separation

This helped evaluate how well the models learned meaningful representations.

---

### 3. Latent Space Interpolation

Interpolation was performed between two latent vectors:

z_interp = (1 − α)z₁ + αz₂

This demonstrated:

* Smooth transitions between clothing categories
* Continuity of the latent space
* Generative capability of the VAE

---

### 4. Loss Function Comparison

The following loss functions were evaluated:

* Binary Cross Entropy (BCE)
* Mean Squared Error (MSE)

Comparison metrics:

* Reconstruction accuracy
* Image sharpness
* Training behavior

---

### 5. Optimizer Comparison

The models were trained using:

* SGD
* RMSprop
* Adam

Comparison metrics:

* Convergence speed
* Training stability
* Loss reduction

---

### 6. Model Evaluation

Models were evaluated based on:

* Reconstruction quality
* Latent space smoothness
* Generation capability
* Interpolation performance
* Training stability

---

## Key Observations

* Autoencoder produced sharper reconstructions
* VAE generated smoother transitions between images
* Increasing latent dimension improved reconstruction quality
* Adam optimizer provided the most stable training
* VAE learned a structured and continuous latent space

---

## Expected Outcomes Achieved

* Better reconstruction sharpness in Autoencoder
* Better generative capability and smoother transitions in VAE
* Meaningful latent space representation for Fashion-MNIST data
* Understanding of probabilistic generative models
* Experience with experiment tracking and model deployment

---

## Technologies Used

* Python
* PyTorch
* NumPy
* Matplotlib
* Scikit-learn
* Weights & Biases
* Hugging Face
* Google Colab

---

## Repository Structure

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

## How to Run the Experiment

1. Clone the repository

```
git clone https://github.com/your-username/experiment-8.git
```

2. Install dependencies

```
pip install torch torchvision matplotlib numpy wandb huggingface_hub
```

3. Run the notebook

```
Open experiment-8.ipynb
Run all cells
```

---

## Submission Links

GitHub Repository:

```
Add your GitHub repository link here
```

Weights & Biases Dashboard:

```
Add your W&B project link here
```

Hugging Face Model Repository:

```
Add your Hugging Face model link here
```

---

## Author

**Name:** Nisha Singh
**Course:** M.Tech
**Subject:** Deep Learning
**Experiment:** Autoencoders and Variational Autoencoders
