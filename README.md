# Cattle Cardiovascular Disease (CVD) Detection using Retina Images

## Problem Statement
Cardiovascular disease (CVD) in cattle poses a significant health risk, leading to economic losses in the livestock industry. Early detection of CVD is crucial for effective treatment and management. This project aims to create an image classification model to identify CVD in cattle by analyzing retina images.

---

## Dataset Description

### Dataset Source
The dataset used for this project was sourced from Kaggle.

### Dataset Structure
The dataset consists of retina images of cattle, organized into two categories:
- `0`: Healthy (No CVD)
- `1`: CVD Present

### Image Details
- **Input:** Retina images of varying resolutions.
- **Output:** Binary classification (Healthy or CVD).

### Preprocessing Steps
- **Normalization:** Pixel values are scaled to the range [0, 1].
- **Resizing:** All images are resized to 254x254 pixels for consistency.
- **Augmentation:** Techniques such as random rotations, flips, zooms, and brightness adjustments are applied to improve robustness.

---

## Methodology

### 1. Data Preprocessing
- Implemented image resizing, normalization, and augmentation.
- Organized images into training, validation, and testing sets.

### 2. Model Architecture
We developed a Convolutional Neural Network (CNN) with the following structure:
- **Convolutional Layers:** Extract spatial features.
- **Pooling Layers:** Reduce spatial dimensions while preserving essential information.
- **Fully Connected Layers:** Flatten and classify feature maps.
- **Dropout Layer:** Added to prevent overfitting.
- **Output Layer:** Single neuron with sigmoid activation for binary classification.

### 3. Training
- **Loss Function:** Binary Crossentropy.
- **Optimizer:** Adam optimizer.
- **Learning Rate Scheduler:** Dynamically reduced learning rate on performance plateaus.
- **Metrics:** Accuracy, Precision, Recall, and F1-score.

### 4. Explainability
Used **Gradient-Weighted Class Activation Mapping (Grad-CAM)** to visualize which areas of the retina influenced the model's predictions.

---

## Results and Evaluation Metrics

### Performance on Test Data
- **Accuracy:** 60.4%
- **Precision:** 59.7%
- **Recall:** 78.4%
- **F1-Score:** 67.8%

### Grad-CAM Visualizations
Grad-CAM heatmaps provided insights into the model's focus areas, enabling interpretable predictions.

---

## Challenges and Solutions

### 1. Imbalanced Dataset
- **Challenge:** The dataset had more healthy images than CVD images.
- **Solution:** Applied oversampling techniques for the minority class and image augmentation to balance the data.

### 2. Overfitting
- **Challenge:** The model showed high performance on training data but lower performance on validation data.
- **Solution:** Added dropout layers and used early stopping during training.

### 3. Explainability
- **Challenge:** Ensuring the model's predictions were interpretable.
- **Solution:** Integrated Grad-CAM for heatmap visualizations of focus areas.

---

## Future Work
- Collect more retina images to enhance model generalization.
- Deploy the model using a web or mobile interface for real-world use by veterinarians.
- Explore advanced architectures like transfer learning to improve performance further.
