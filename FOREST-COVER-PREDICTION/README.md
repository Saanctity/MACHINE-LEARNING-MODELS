# Forest Cover Type Prediction

Machine learning model to predict forest cover types in Roosevelt National Forest, Colorado.

## Dataset

- **Samples**: 15,120
- **Features**: 56
- **Classes**: 7 (Spruce/Fir, Lodgepole Pine, Ponderosa Pine, Cottonwood/Willow, Aspen, Douglas-fir, Krummholz)
- **Split**: 80/20 train-test

## Features

**Original**: Elevation, Aspect, Slope, Distance to Hydrology/Roadways/Fire Points, Hillshade (9am/Noon/3pm), Wilderness Area (4 binary), Soil Type (40 binary)

**Engineered**: Distance_To_Hydrology, Mean_Distance, Mean_Hillshade, Hillshade_Range

## Models & Results

| Model | Test Accuracy | F1-Score |
|-------|--------------|----------|
| Random Forest | 84.4% | 84.1% |
| **Gradient Boosting** | **85.6%** | **85.4%** |

## Key Insights

1. **Elevation dominates** - 44% feature importance
2. **Best performers**: Cottonwood/Willow (95%), Krummholz (96%)
3. **Weakest**: Lodgepole Pine (66% recall)
4. Geographic distances are critical predictors

## Installation & Usage

```bash
pip install -r requirements.txt
python forest_cover_model.py
```

**Runtime**: 2-3 minutes

## Top Features

1. Elevation (44.0%)
2. Mean_Distance (6.0%)
3. Horizontal_Distance_To_Fire_Points (5.7%)
4. Horizontal_Distance_To_Roadways (5.4%)
5. Distance_To_Hydrology (4.9%)

## Project Structure

```
├── train.csv
├── FOREST_COVER_PREDICTION.ipynb
├── requirements.txt
└── README.md
```

---

**Final Performance**: 85.6% accuracy on 7-class classification