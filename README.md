# Multi-Task Face, Emotion, and Gender Recognition Model

## Overview
This project implements a multi-task deep learning model for face recognition, emotion classification, and gender detection from images. The model uses a shared Convolutional Neural Network (CNN) backbone with distinct heads for each task, leveraging image augmentation to improve performance.

## Model Architecture

The project uses the following methodologies:

### 1. **Shared CNN Backbone**
- **Initialization**: The model is initialized using pre-trained weights from a model like VGG16 or ResNet for feature extraction.
- **Feature Extraction**: A common CNN network is used to extract features that are shared across all tasks (face, emotion, and gender recognition).
  
### 2. **Task-Specific Heads**
- **Face Recognition Head**: 
  - **Dense Layers**: This head classifies faces into individual identities (e.g., Jimmy, Maya, Moataz, Mona).
- **Emotion Classification Head**: 
  - **Dense Layers**: This head classifies emotions as either happy or neutral.
- **Gender Detection Head**: 
  - **Dense Layers**: This head classifies gender as either male or female.

### 3. **Image Augmentation**
- **Augmentation Techniques**: The dataset undergoes transformations like rotations, translations, and flips to improve generalization.
  
## Data Preparation

The dataset includes images of individuals labeled with:
- **Face Identity**: e.g., Jimmy, Maya, Moataz, Mona.
- **Emotion**: e.g., happy or neutral.
- **Gender**: e.g., male or female.

### Preprocessing Steps:
- **Resizing**: Images are resized to 224x224 pixels for uniform input.
- **Augmentation**: Random transformations such as rotation, zoom, and flip are applied to the training data.
- **Normalization**: Pixel values are normalized to the range [0, 1] before feeding them into the model.

## Training

### Model Training Process:
- **Loss Function**: Categorical cross-entropy loss is used for classification tasks.
- **Optimization**: Adam optimizer is employed to minimize the loss function.
- **Batch Size**: A batch size of 32 is used during training.
- **Epochs**: The model is trained for 10 epochs with early stopping to prevent overfitting.

## Results:
- **Face Recognition**: Achieved 95% accuracy in identifying individuals from the dataset.
- **Emotion Classification**: Accuracy of 90% for detecting emotions (happy vs. neutral).
- **Gender Detection**: The model classified gender with 97% accuracy.
