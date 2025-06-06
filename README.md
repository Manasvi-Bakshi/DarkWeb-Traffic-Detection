# DarkWeb

Network Traffic Classification with Machine Learning

This project aimed at detecting and classifying types of network traffic in the DarkWeb. The goal was to apply traditional Machine Learning Algorithms and better understand them on real world data.

## Dataset

The **CIC-Darknet 2020** dataset, is a comprehensive traffic dataset which is available online the link to which is provided [here](https://www.unb.ca/cic/datasets/darknet2020.html).

- 23,923 total records
- Features engineered from network flow data
- 4 Target labels: `Tor`, `VPN`, `NonVPN`, `Non-Tor`


## What This Project Does

- Cleaned and aligned two datasets (features + labels)
- Encoded the categorical labels using `LabelEncoder`
- Split the dataset into train-test sets
- Trained three classification models:
  - **Logistic Regression**
  - **Random Forest**
  - **Support Vector Machine (SVM)**
- Evaluated the models using:
  - Precision, Recall, F1-Score
  - Accuracy
  - Confusion Matrix
- Visualized performance using seaborn heatmaps and comparison plots
- Exported models as `.pth` files using `joblib`

---

##  Evaluation


| Model               | Accuracy | Macro F1 | Tor F1 | Precision |
|---------------------|----------|----------|--------|--------|
| Logistic Regression | 0.59     | 0.46     | 0.00   | 0.48   |
| Random Forest       | 0.72     | 0.51     | 0.00   | 0.51   |
| SVM                 | 0.70     | 0.55     | 0.00   | 0.57   |

> Note: The `Tor` class has very low representation and is under-predicted across all models, indicating **class imbalance** or feature insufficiency for Tor detection. This confirms the fact that traditional Machine Learning algorithms struggle with dealing with highly biased
and imbalanced data.

## How to Run in Google Colab

1. Upload your dataset files (`df` and `reduced_df`) as required.
2. Run all cells in order:
   - Preprocessing and alignment
   - Model training and evaluation
   - Visualization
   - Save models to `.pth`
3. Models are saved using `joblib` and can be reloaded easily later.

## Model Saving

All trained models are saved using `joblib`:

- `logistic_regression_model.pth`
- `random_forest_model.pth`
- `svm_model.pth`

These files can be loaded again with:
```python
model = joblib.load('model_name.pth')
