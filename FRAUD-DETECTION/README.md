# Fraud Transaction Detection System

## Project Overview
A machine learning system that detects fraudulent transactions using Random Forest classification. The model achieves **96.75% accuracy** and **96% fraud detection rate** while processing transactions in under 5 minutes.

## Dataset Description
The dataset contains simulated transaction data with the following fraud scenarios:

1. **Scenario 1**: Transactions exceeding $220 are fraudulent
2. **Scenario 2**: Compromised terminals - Random terminals are compromised for 28-day periods
3. **Scenario 3**: Stolen credentials - Customer accounts are compromised with inflated transaction amounts

### Dataset Columns
- `TRANSACTION_ID`: Unique transaction identifier
- `TX_DATETIME`: Transaction timestamp
- `CUSTOMER_ID`: Unique customer identifier
- `TERMINAL_ID`: Unique terminal identifier
- `TX_AMOUNT`: Transaction amount
- `TX_FRAUD`: Binary label (0 = Legitimate, 1 = Fraud)

## Features Engineered

### Temporal Features
- Hour, day, weekday, and month of transaction

### Customer Behavior Features
- Average, standard deviation, max, min transaction amounts
- Transaction count per customer
- Ratio of current transaction to customer average
- Ratio of current transaction to customer maximum

### Terminal Risk Features
- Terminal fraud rate
- Terminal average transaction amount
- Terminal transaction count

### Direct Detection
- High amount flag (>$220)

## Model Performance

| Metric | Value |
|--------|-------|
| Accuracy | 96.75% |
| ROC-AUC Score | 0.9895 |
| Fraud Detection Rate (Recall) | 96% |
| False Negatives | 14 out of 330 frauds |

### Confusion Matrix
```
              Predicted Legitimate  Predicted Fraud
Legitimate         38,383              1,287
Fraud                 14                316
```

## Key Insights
- **TERMINAL_FRAUD_RATE** is the most important feature (78% importance)
- Model prioritizes catching frauds over minimizing false alarms
- Optimized for real-world deployment with fast inference time

## Installation

### Requirements
```bash
pip install -r requirements.txt
```

### Running on Google Colab
1. Upload `dataset.zip` to Colab
2. Upload the notebook file
3. Run all cells
4. Model trains in ~20 seconds

## Usage

```python
# The notebook automatically:
# 1. Extracts data from dataset.zip
# 2. Loads all PKL files from the data folder
# 3. Engineers features
# 4. Trains the model
# 5. Outputs performance metrics
```

## Model Architecture
- **Algorithm**: Random Forest Classifier
- **Estimators**: 50 trees
- **Max Depth**: 10
- **Class Weight**: Balanced (handles imbalanced dataset)
- **Training Time**: ~20 seconds on 200k samples

## Optimization Strategy
- Samples 200,000 transactions from 1.7M total for speed
- Maintains near-identical performance to full dataset
- Reduces training time from 7 minutes to 20 seconds

## Results Interpretation
- **High Recall (96%)**: Catches nearly all fraudulent transactions
- **Low Precision (20%)**: Results in more false alarms, but acceptable for fraud detection
- **Trade-off**: Better to review extra transactions than miss actual fraud

## Future Improvements
- Real-time fraud detection pipeline
- Advanced ensemble methods (XGBoost, LightGBM)
- Deep learning approaches for sequential pattern detection
- Integration with transaction monitoring systems

## File Structure
```
project/
│
├── dataset.zip
│   └── data/
│       ├── 2018-04-01.pkl
│       ├── 2018-04-02.pkl
│       └── ... (183 files)
│
├── fraud_detection.ipynb
├── README.md
└── requirements.txt
```

## Author
Developed as part of an internship project focused on fraud detection systems.

## License
This project is for educational and demonstration purposes.