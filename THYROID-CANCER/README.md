# Thyroid Cancer Recurrence Prediction

Machine learning system to predict thyroid cancer recurrence using clinical patient data.

## Dataset
- **383 patients** with 16 clinical features
- **28.2% recurrence rate**
- **80/20 train-test split** with stratification

## Approach

### Feature Selection
Removed 5 features that could introduce data leakage (Response, Stage, T, N, M) as they're measured during follow-up. Final model uses **11 pre-treatment features** available at diagnosis.

### Models Trained
- Logistic Regression
- Random Forest
- Gradient Boosting
- XGBoost
- Voting Ensemble

### Validation
- 5-fold stratified cross-validation
- Primary metric: AUC-ROC
- Secondary: Accuracy, Precision, Recall

## Results

### Best Model: Random Forest
- **Test AUC:** 0.9669
- **Cross-Validation AUC:** 0.9332 (±0.0297)
- **Accuracy:** 89.61%

### Classification Performance
```
                  Precision    Recall    F1-Score
No Recurrence        0.92       0.95       0.93
Recurrence           0.83       0.73       0.78
```

### Top Predictive Features
1. **Risk** (43.29%) - Clinical risk classification
2. **Adenopathy** (20.47%) - Lymph node involvement
3. **Age** (12.31%) - Patient age at diagnosis
4. **Focality** (5.33%) - Tumor spread pattern
5. **Gender** (5.01%) - Biological factors

## Key Findings

- Strong predictive performance using only pre-treatment features
- Balanced feature importance indicates clinically meaningful patterns
- Cross-validation stability confirms model generalization
- Risk classification and lymph node status are primary predictors

## Technical Stack
```
pandas, numpy, scikit-learn, xgboost, matplotlib, seaborn
```

## Usage
**Google Colab:**
1. Upload notebook
2. Run all cells
3. Upload CSV when prompted
4. Runtime: < 5 minutes

## Files
- `thyroid_cancer_prediction.ipynb` - Main notebook
- `requirements.txt` - Dependencies
- `README.md` - Documentation
- `thyroid_prediction_results.png` - Visualizations# Thyroid Cancer Recurrence Prediction

Machine learning system to predict thyroid cancer recurrence using clinical patient data.

## Dataset
- **383 patients** with 16 clinical features
- **28.2% recurrence rate**
- **80/20 train-test split** with stratification

## Approach

### Feature Selection
Removed 5 features that could introduce data leakage (Response, Stage, T, N, M) as they're measured during follow-up. Final model uses **11 pre-treatment features** available at diagnosis.

### Models Trained
- Logistic Regression
- Random Forest
- Gradient Boosting
- XGBoost
- Voting Ensemble

### Validation
- 5-fold stratified cross-validation
- Primary metric: AUC-ROC
- Secondary: Accuracy, Precision, Recall

## Results

### Best Model: Random Forest
- **Test AUC:** 0.9669
- **Cross-Validation AUC:** 0.9332 (±0.0297)
- **Accuracy:** 89.61%

### Classification Performance
```
                  Precision    Recall    F1-Score
No Recurrence        0.92       0.95       0.93
Recurrence           0.83       0.73       0.78
```

### Top Predictive Features
1. **Risk** (43.29%) - Clinical risk classification
2. **Adenopathy** (20.47%) - Lymph node involvement
3. **Age** (12.31%) - Patient age at diagnosis
4. **Focality** (5.33%) - Tumor spread pattern
5. **Gender** (5.01%) - Biological factors

## Key Findings

- Strong predictive performance using only pre-treatment features
- Balanced feature importance indicates clinically meaningful patterns
- Cross-validation stability confirms model generalization
- Risk classification and lymph node status are primary predictors

## Technical Stack
```
pandas, numpy, scikit-learn, xgboost, matplotlib, seaborn
```

## Usage
**Google Colab:**
1. Upload notebook
2. Run all cells
3. Upload CSV when prompted
4. Runtime: < 5 minutes

## Files
- `thyroid_cancer_prediction.ipynb` - Main notebook
- `requirements.txt` - Dependencies
- `README.md` - Documentation
- `thyroid_prediction_results.png` - Visualizations

## Model Configuration
```python
RandomForestClassifier(
    n_estimators=200,
    max_depth=8,
    min_samples_split=10,
    random_state=42
)
```

---
*Developed for research and educational purposes. Clinical deployment requires additional validation.*

## Model Configuration
```python
RandomForestClassifier(
    n_estimators=200,
    max_depth=8,
    min_samples_split=10,
    random_state=42
)
```

---
*Developed for research and educational purposes. Clinical deployment requires additional validation.*