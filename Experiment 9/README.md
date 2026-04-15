# 🧪 Experiment 9: Generative Adversarial Networks (GANs) with Model Variants and Experimental Analysis

---

## 📌 Objective

The objective of this experiment is to implement and analyze **Generative Adversarial Networks (GANs)** for image generation using the **Fashion-MNIST** dataset.

A GAN consists of two competing neural networks:

* **Generator** — creates fake images
* **Discriminator** — distinguishes real vs fake images

This experiment aims to study:

* The effect of model architecture (**Vanilla GAN vs DCGAN**)
* The impact of different loss functions and optimizers
* Training stability and convergence behavior
* Generated image quality and diversity

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

* **Training**
* **Validation**
* **Testing** (if required)

---

## ⚙️ Preprocessing and Augmentation

The following preprocessing steps were applied:

* Normalization of pixel values to **[-1, 1]**
* Image scaling compatible with **Tanh activation**
* Batch loading using PyTorch DataLoader

### Optional Augmentation

* Horizontal Flip (not applied to preserve semantic meaning of clothing items)

---

## 🏗️ Model Architectures

---

# 1️⃣ Generator Network

The Generator takes random noise from latent space and generates new images.

### Input

* Random noise vector (latent space)

### Output

* Generated image (28 × 28 grayscale)

---

## Vanilla GAN Generator

Architecture:

* Fully connected layers
* ReLU activation
* Tanh output

Structure:

```text
Noise → Linear → Linear → Linear → Image
```

---

## DCGAN Generator

Architecture:

* Transposed Convolution layers
* Batch Normalization
* ReLU activation
* Tanh output

Structure:

```text
Noise → ConvTranspose → BatchNorm → ReLU → Image
```

---

# 2️⃣ Discriminator Network

The Discriminator evaluates whether an image is real or fake.

### Input

* Image (real or generated)

### Output

* Probability (real or fake)

---

## Vanilla GAN Discriminator

Architecture:

* Fully connected layers
* LeakyReLU activation
* Sigmoid output

Structure:

```text
Image → Linear → Linear → Probability
```

---

## DCGAN Discriminator

Architecture:

* Convolution layers
* Batch Normalization
* LeakyReLU activation
* Sigmoid output

Structure:

```text
Image → Conv → BatchNorm → Probability
```

---

# 3️⃣ Adversarial Training

The Generator and Discriminator are trained alternately.

Training steps:

1. Train Discriminator on real images
2. Train Discriminator on fake images
3. Train Generator to fool the Discriminator

Baseline Loss Function:

* Binary Cross Entropy (**BCE**)

---

# 4️⃣ Loss Functions

The following loss functions were implemented and compared:

* Binary Cross Entropy (**BCE**)
* Least Squares GAN (**LSGAN**)
* Wasserstein Loss (**WGAN**)

Comparison metrics:

* Training stability
* Loss convergence
* Generated image quality

---

# 5️⃣ Optimizers

Models were trained using:

* **SGD**
* **RMSprop**
* **Adam**

Comparison metrics:

* Convergence speed
* Stability of training
* Loss behavior

---

# 6️⃣ Training Process

The training process included:

* Training discriminator on real and fake images
* Training generator to fool the discriminator
* Updating weights alternately
* Logging training metrics

Metrics tracked:

* Generator loss
* Discriminator loss

---

# 7️⃣ Training and Experiment Tracking

All metrics were logged using **Weights & Biases**.

Tracked metrics:

* Generator loss curve
* Discriminator loss curve
* Generated images over epochs

This enabled monitoring of:

* Training stability
* Convergence behavior
* Image generation progress

---

# 8️⃣ Model Logging and Deployment

The trained models were saved and uploaded for reproducibility.

Platforms used:

* Weights & Biases
* Hugging Face
* GitHub

Models uploaded:

* Generator models
* Trained outputs

---

# 9️⃣ Evaluation

Models were evaluated based on:

### Visual Quality

* Clarity of generated images
* Realistic clothing shapes

### Diversity

* Variety of generated outputs
* Absence of repeated patterns

### Training Stability

* Loss convergence behavior
* Smooth training dynamics

---

## Comparisons Performed

* Vanilla GAN vs DCGAN
* Different loss functions
* Different optimizers
* Effect of augmentation (if applied)

---

# 10️⃣ Analysis and Discussion

---

## GAN vs DCGAN

Key findings:

* DCGAN produced higher quality images
* Convolution layers improved spatial feature learning
* Batch normalization stabilized training

---

## Loss Function Comparison

### BCE

* Stable baseline loss
* Simple implementation

### LSGAN

* Reduced vanishing gradient problem
* More stable training

### WGAN

* Improved gradient behavior
* Better convergence stability

---

## Optimizer Comparison

### SGD

* Slower convergence
* Less stable training

### RMSprop

* Moderate stability
* Faster than SGD

### Adam

* Most stable training
* Faster convergence
* Best performance overall

---

## Training Challenges Observed

Common GAN issues:

* Mode collapse
* Vanishing gradients
* Oscillatory training behavior

These challenges were monitored using:

* Loss curves
* Generated image inspection

---

# 11️⃣ Observations

Key observations during training:

* Generator improved image quality over epochs
* Loss values fluctuated due to adversarial training
* DCGAN generated smoother and more realistic images
* Training performance was sensitive to hyperparameters

---

# 🎯 Expected Outcomes Achieved

* Improved image quality using DCGAN
* Better training stability with Adam optimizer
* Clear understanding of GAN training dynamics
* Successful implementation of adversarial learning
* Experience with experiment tracking and model deployment

---

# 🛠️ Technologies Used

* Python
* PyTorch
* NumPy
* Matplotlib
* Torchvision
* Weights & Biases
* Hugging Face
* Google Colab

---

# 📁 Repository Structure

```text
experiment-9/
│
├── experiment-9.ipynb
├── README.md
│
├── models/
│   ├── Vanilla-GAN-BCE-Adam.pth
│   ├── DCGAN-BCE-Adam.pth
│   ├── DCGAN-LSGAN-Adam.pth
│   └── DCGAN-WGAN-Adam.pth
│
├── plots/
│   ├── generator_loss_curve.png
│   ├── discriminator_loss_curve.png
│   ├── generated_images.png
│   └── model_comparison.png
```

---

# ▶️ How to Run the Experiment

## Step 1 — Clone the Repository

```bash
git clone https://github.com/your-username/experiment-9.git
```

## Step 2 — Install Dependencies

```bash
pip install torch torchvision matplotlib numpy wandb huggingface_hub
```

## Step 3 — Run the Notebook

```text
Open experiment-9.ipynb
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

The implementation of **Vanilla GAN** and **DCGAN** successfully demonstrated the ability to generate realistic images from random noise using adversarial learning.

Key conclusions:

* DCGAN achieved better image quality than Vanilla GAN
* Adam optimizer provided the most stable training
* Loss functions influenced convergence behavior
* GAN training requires careful monitoring and tuning

This experiment provided practical experience with generative models, adversarial training, and experiment tracking.

---

## 👩‍💻 Author

**Nisha Singh**
**B.Tech — Deep Learning Lab**
**Experiment 9: Generative Adversarial Networks**
