# Mobile Phone Price Prediction 📱

A machine learning model that predicts mobile phone pricing categories (Low/Medium/High/Very High) based on device specifications.

## 🎯 Objective

Build a classification system to predict mobile phone price ranges using technical specifications and features.

## 📊 Dataset Features

- **Battery & Hardware**: battery_power, ram, int_memory, mobile_wt, n_cores
- **Display**: px_height, px_width, sc_h, sc_w, touch_screen
- **Camera**: fc (front), pc (primary)
- **Connectivity**: blue, wifi, four_g, three_g, dual_sim
- **Other**: clock_speed, m_dep, talk_time

**Target Variable**: `price_range` (0=Low, 1=Medium, 2=High, 3=Very High)

## 🚀 Quick Start

### Google Colab (Recommended)
1. Open the notebook in Google Colab
2. Upload your `dataset.csv` when prompted
3. Run all cells

### Local Setup
```bash
pip install -r requirements.txt
python mobile_price_prediction.py
```

## 📈 Model Performance

- **Accuracy**: 88.75%
- **Algorithm**: Random Forest Classifier
- **Training Time**: < 3 minutes
- **Cross-Validation**: 86.94% (±0.78%)

### Class-wise Performance
| Price Range | Precision | Recall | F1-Score |
|-------------|-----------|--------|----------|
| Low Cost | 94% | 96% | 95% |
| Medium Cost | 83% | 81% | 82% |
| High Cost | 83% | 82% | 82% |
| Very High Cost | 95% | 96% | 96% |

## 📁 Output Files

- `price_analysis.png` - Feature correlation and distribution plots
- `confusion_matrix.png` - Model prediction accuracy visualization
- `feature_importance.png` - Top contributing features

## 🔑 Key Features

- Automated data exploration and visualization
- Feature correlation analysis
- Standardized preprocessing pipeline
- Production-ready prediction function
- Comprehensive model evaluation

## 💡 Usage Example

```python
# Predict price for a new phone
prediction = predict_price(
    battery_power=3000,
    blue=1,
    clock_speed=2.5,
    dual_sim=1,
    fc=5,
    four_g=1,
    int_memory=64,
    m_dep=0.7,
    mobile_wt=150,
    n_cores=8,
    pc=20,
    px_height=1920,
    px_width=1080,
    ram=3500,
    sc_h=15,
    sc_w=8,
    talk_time=10,
    three_g=1,
    touch_screen=1,
    wifi=1
)
print(prediction)  # Output: 'Very High Cost'
```

## 📦 Requirements

See `requirements.txt` for dependencies.

## 🎓 Model Insights

**Most Important Features:**
1. RAM (highest correlation with price)
2. Battery Power
3. Pixel Resolution (width & height)
4. Internal Memory

---

**Built with** 🐍 Python | 🤖 Scikit-learn | 📊 Pandas

---

# requirements.txt

```txt
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=1.0.0
```