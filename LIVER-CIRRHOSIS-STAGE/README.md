# Liver Cirrhosis Stage Detection 🏥

A machine learning system that predicts the histologic stage of liver cirrhosis (Stage 1, 2, or 3) based on patient clinical data.

## 📊 Project Overview

This project builds a Random Forest classification model to detect the severity of liver damage in patients with primary biliary cirrhosis (PBC). The model analyzes 18 clinical features to predict disease stage.

**Model Performance:**
- **Test Accuracy:** 91.62%
- **F1 Score:** 0.9164
- **Training Time:** < 5 minutes

## 🎯 Objective

Predict liver cirrhosis stage (1, 2, or 3) from patient clinical data.

## 📁 Dataset

**Source:** Mayo Clinic study on primary biliary cirrhosis (1974-1984)

**Size:** 25,000 patient records

**Features (18):**
- N_Days, Status, Drug, Age, Sex
- Ascites, Hepatomegaly, Spiders, Edema
- Bilirubin, Cholesterol, Albumin, Copper
- Alk_Phos, SGOT, Tryglicerides, Platelets, Prothrombin

**Target:** Stage (1, 2, or 3)

## 🛠️ Technology Stack

- Python 3.8+
- scikit-learn
- pandas, numpy
- matplotlib, seaborn
- Google Colab

## 📦 Installation

```bash
pip install -r requirements.txt
```

## 🚀 Usage

1. Upload `liver_cirrhosis_detection.ipynb` to Google Colab
2. Upload `liver_cirrhosis.csv` dataset
3. Run all cells

## 📈 What We Did

1. **Data Exploration**
   - Loaded dataset and analyzed distributions
   - Visualized stage distribution and key features
   - Checked for missing values (none found)

2. **Data Preprocessing**
   - Encoded 7 categorical variables (Status, Drug, Sex, Ascites, Hepatomegaly, Spiders, Edema)
   - Scaled numerical features using StandardScaler
   - Split data: 80% train (20,000), 20% test (5,000)

3. **Model Training**
   - Random Forest Classifier (100 trees, max_depth=10)
   - 5-fold cross-validation: 91.23% ± 0.89%

4. **Evaluation**
   - Confusion matrix
   - Classification report
   - Feature importance analysis

## 📊 Results

| Metric | Score |
|--------|-------|
| Training Accuracy | 92.45% |
| Testing Accuracy | 91.62% |
| F1 Score | 0.9164 |

**Per-Stage Performance:**
- Stage 1: Precision 0.91, Recall 0.92
- Stage 2: Precision 0.92, Recall 0.91
- Stage 3: Precision 0.92, Recall 0.92

## 🔍 Key Insights

**Top 5 Important Features:**
1. Bilirubin - Most predictive biomarker
2. Albumin - Protein synthesis indicator
3. Copper - Accumulation marker
4. Prothrombin - Blood clotting factor
5. Age - Disease progression factor

**Findings:**
- Balanced performance across all three stages
- Biochemical markers (Bilirubin, Albumin, Copper) are strongest predictors
- Model shows no class bias
- Fast execution makes it practical for real-time use

## 📂 Project Structure

```
liver-cirrhosis-detection/
│
├── liver_cirrhosis_detection.ipynb    # Main notebook
├── liver_cirrhosis.csv                # Dataset
├── README.md                          # Documentation
└── requirements.txt                   # Dependencies
```

## 👨‍💻 Author

Sagar Shukla