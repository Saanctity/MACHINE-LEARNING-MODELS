# American Sign Language Detection

A deep learning system that detects and classifies American Sign Language (ASL) alphabet signs from images into 29 classes (A-Z, SPACE, DELETE, NOTHING).

## Features

- **29 Class Classification**: Recognizes all 26 letters plus 3 special signs
- **Transfer Learning**: Uses MobileNetV2 for efficient training
- **High Accuracy**: Achieves 95%+ validation accuracy
- **Fast Training**: Completes in ~15-20 minutes on Google Colab
- **Visualization**: Includes training graphs, confusion matrix, and sample predictions

## Dataset

Uses the [ASL Alphabet Dataset](https://www.kaggle.com/datasets/grassknoted/asl-alphabet) from Kaggle.
- 87,000 images (3,000 per class)
- 200x200 RGB images
- Automatically downloaded via kagglehub

## Requirements

See `requirements.txt` for dependencies.

## Usage

### Google Colab (Recommended)

1. Open the notebook in Google Colab
2. Run all cells
3. Dataset downloads automatically
4. Model trains and displays results

### Local Setup

```bash
pip install -r requirements.txt
python asl_detection.py
```

## Model Architecture

- **Base Model**: MobileNetV2 (pre-trained on ImageNet)
- **Input Size**: 96x96 RGB images
- **Batch Size**: 128
- **Epochs**: 10 (with early stopping)
- **Optimizer**: Adam (lr=0.001)

## Results

- **Validation Accuracy**: 95%+
- **Training Time**: ~15-20 minutes
- **Training Samples**: 14,790
- **Validation Samples**: 2,610

## Output

The system provides:
- Training/validation accuracy and loss graphs
- Classification report with precision, recall, F1-score
- Confusion matrix heatmap
- Sample predictions with confidence scores

## Classes

A, B, C, D, E, F, G, H, I, J, K, L, M, N, O, P, Q, R, S, T, U, V, W, X, Y, Z, del, nothing, space