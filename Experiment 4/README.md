# Experiment 4: Image Classification using Convolutional Neural Networks

## Objective
The objective of this experiment is to perform image classification using Convolutional Neural Networks (CNNs) and to compare the performance of a custom CNN with a pretrained ResNet-18 model.

## Datasets Used
- **Cats vs Dogs** (Kaggle)
- **CIFAR-10** (Torchvision)

## Models Implemented
1. **Custom CNN**
   - Two convolutional layers with max pooling
   - Batch Normalization and Dropout for regularization
   - Multiple activation functions (ReLU, Tanh, LeakyReLU)
   - Hyperparameter tuning using different initialization methods and optimizers

2. **ResNet-18 (Pretrained)**
   - Initialized with ImageNet weights
   - Pretrained layers frozen
   - Final fully connected layer retrained for classification

## Methodology
1. Data preprocessing and normalization  
2. Hyperparameter tuning using a 3×3×3 combination of:
   - Activation functions
   - Weight initialization methods
   - Optimizers
3. Selection of the best CNN configuration based on validation accuracy  
4. Retraining the best CNN for 15 epochs  
5. Fine-tuning ResNet-18 for comparison  
6. Visualization of training performance and prediction results  

## Results and Observations
- The custom CNN achieved higher accuracy than ResNet-18 on both datasets.
- This is attributed to full end-to-end training and optimized hyperparameters for the custom CNN.
- ResNet-18 performance was limited due to freezing pretrained layers, which restricted dataset-specific feature adaptation.

## Saved Model Weights
Due to GitHub file size limitations, the pretrained ResNet-18 model weights are provided via Google Drive.

### Custom CNN Weights (Available in Repository)
- `best_cnn_catsdogs.pth`
- `best_cnn_cifar10.pth`

### ResNet-18 Weights (Google Drive)
- **Cats vs Dogs ResNet-18**:  
  🔗 https://drive.google.com/file/d/1MMZ1v5Y20S1PZUWoaLs99lEwKuiyAocA/view?usp=sharing
- **CIFAR-10 ResNet-18**:  
  🔗 https://drive.google.com/file/d/1Iy_NtGgKJdoPARgtnSLBrK-e5nVqjIcu/view?usp=sharing
## Conclusion
This experiment demonstrates that a well-tuned custom CNN can outperform a pretrained deep network on smaller datasets. While ResNet-18 provides strong general features through transfer learning, full retraining and dataset-specific optimization can yield better results for task-specific models.
