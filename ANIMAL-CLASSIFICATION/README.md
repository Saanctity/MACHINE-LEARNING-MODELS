# 🐾 Animal Image Classification

A deep learning project that classifies 15 different animal species using Transfer Learning with MobileNetV2.

## 📋 Overview

This project uses a pre-trained MobileNetV2 model fine-tuned on a custom dataset of 450 animal images across 15 classes. The model achieves high accuracy through a two-phase training approach.

## 🦁 Animal Classes

Bear, Bird, Cat, Cow, Deer, Dog, Dolphin, Elephant, Giraffe, Horse, Kangaroo, Lion, Panda, Tiger, Zebra

## 🚀 Features

- **Transfer Learning**: Leverages MobileNetV2 pre-trained on ImageNet
- **Data Augmentation**: Improves model generalization
- **Two-Phase Training**: Initial classifier training followed by fine-tuning
- **Comprehensive Evaluation**: Classification reports, confusion matrix, and sample predictions
- **Visualization**: Training curves and model performance metrics

## 📦 Installation

```bash
pip install -r requirements.txt
```

## 💻 Usage

1. **Prepare Dataset**: Organize images in the following structure:
   ```
   Animal Classification/dataset/
   ├── Bear/
   ├── Bird/
   ├── Cat/
   └── ... (other animal folders)
   ```

2. **Run the Model**: Open the notebook in Google Colab and execute all cells. Upload your dataset ZIP when prompted.

3. **View Results**: The notebook will display:
    - Dataset distribution
    - Training progress
    - Accuracy and loss curves
    - Confusion matrix
    - Sample predictions

## 🎯 Model Architecture

- **Base Model**: MobileNetV2 (pre-trained on ImageNet)
- **Custom Head**:
    - GlobalAveragePooling2D
    - Dense layers with BatchNormalization and Dropout
    - Softmax output layer (15 classes)

## 📊 Configuration

- **Image Size**: 160x160 pixels
- **Batch Size**: 32
- **Epochs**: 25 (with early stopping)
- **Train/Validation Split**: 80/20

## 🏆 Performance

The model typically achieves:
- **Accuracy**: 80%+ on validation data
- **Training Time**: ~15-20 minutes (on GPU)

## 🛠️ Technologies

- TensorFlow/Keras
- MobileNetV2
- OpenCV
- Matplotlib/Seaborn
- Scikit-learn
