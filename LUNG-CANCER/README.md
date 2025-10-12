# Lung Cancer Survival Prediction

## Overview
Machine learning model to predict patient survival based on lung cancer diagnosis data. The system analyzes patient demographics, medical history, cancer stage, and treatment information to predict survival outcomes.

## Dataset
- **Size**: 890,000 patient records
- **Target**: Binary classification (Survived: 1, Not Survived: 0)
- **Features**: 16 input features including age, gender, BMI, cancer stage, treatment type, comorbidities, etc.

## Features
- Comprehensive feature engineering (risk scores, interactions, normalized features)
- Class imbalance handling using weighted classification
- Multiple model comparison (Random Forest, XGBoost)
- Visual performance analysis (confusion matrix, ROC curve, feature importance)

## Installation

### Requirements
```bash
pip install -r requirements.txt
```

### Run in Google Colab
1. Upload `dataset_med.csv` to Colab
2. Run the notebook cells sequentially
3. Results and visualizations will be generated automatically

## Model Performance

| Model | Accuracy | ROC-AUC | F1-Score |
|-------|---------|--------|---------|
| Random Forest | 74.94%| 0.4995| 0.0844|
| XGBoost | 53.23% | 0.5000 | 0.2924 |

**Best Model**: Random Forest with 74.94% accuracy

### Performance Notes
- **Accuracy**: 74.94% indicates reasonable classification performance
- **ROC-AUC ≈ 0.50**: Suggests limited discriminative power of available features
- **Low F1-Score**: Model tends to predict majority class due to data imbalance

The ROC-AUC score indicates that the current features have weak predictive relationships with survival outcomes. Real-world clinical applications would require additional features like tumor size, genetic markers, and treatment response metrics.

## Project Structure
```
├── LUNG_CANCER.ipynb          # Main notebook
├── dataset_med.csv            # Dataset (not included)
├── README.md                  # This file
├── requirements.txt           # Dependencies
└── results_final.png          # Generated visualizations
```

## Usage

### Training
```python
# Load data
df = pd.read_csv('dataset_med.csv')

# The notebook handles:
# - Feature engineering
# - Model training
# - Evaluation
# - Visualization generation
```

### Output
- **Confusion Matrix**: Shows prediction distribution
- **ROC Curve**: Displays model discrimination ability
- **Feature Importance**: Top 15 influential features
- **Classification Report**: Detailed metrics per class

## Key Findings
1. **Treatment duration** and **cancer stage** are among the most important predictors
2. **Comorbidities** and **age-related features** contribute to risk assessment
3. Model achieves acceptable accuracy but reveals dataset limitations in survival prediction

## Limitations
- ROC-AUC ≈ 0.50 indicates random-level discrimination
- Missing critical clinical features (tumor characteristics, genetic markers)
- Class imbalance (78% not survived vs 22% survived)
- Model may be overfitting to majority class

## Future Improvements
- Collect additional clinical features (tumor size, staging details, biomarkers)
- Implement advanced resampling techniques (SMOTE, ADASYN)
- Ensemble methods with stacking
- Explore deep learning approaches
- Cross-validation for robust evaluation

## Requirements
- Python 3.7+
- See `requirements.txt` for package dependencies

## Runtime 
- **Training Time**: ~ 8 minutes on Google Colab (GPU)
- **Dataset Size**: 890K records