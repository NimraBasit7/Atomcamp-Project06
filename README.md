# Atomcamp-Project06
# Higgs Boson Machine Learning Challenge: Binary Classification

This repository contains my approach to solving a binary classification problem inspired by the [Higgs Boson Machine Learning Challenge](https://www.kaggle.com/competitions/higgs-boson). The goal is to accurately classify particle collision events as signal (1) or background (0).
---

## 🧠 Models Used

### 1. Multilayer Perceptron (MLP)
- **Architecture:** 3 hidden layers (128 → 64 → 32 neurons), ReLU activations.
- **Regularization:** BatchNormalization and Dropout after each dense layer.
- **Training Details:**
  - Loss: Binary Crossentropy
  - Optimizer: Adam
  - Learning rate scheduling: `ReduceLROnPlateau`
  - Early stopping on validation loss

### 2. XGBoost Classifier
- Tuned for depth, learning rate, and number of estimators.
- Achieved higher precision and ROC-AUC compared to MLP.

---

## 📊 Performance Summary

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|-------|----------|-----------|--------|----------|---------|
| MLP (with regularization) | ~84% | Moderate | Moderate | Good | ~0.84 |
| XGBoost | **84%** | **0.87 (class 0)** | **0.74 (class 1)** | **0.84 (avg)** | **0.91** ✅ |

---

## 💡 Insights

- **Depth & Activations:** ReLU with 3-layer MLP improved learning capacity but required regularization to avoid overfitting.
- **Overfitting Mitigation:** Dropout, BatchNorm, EarlyStopping, and LR scheduling helped stabilize performance.
- **Optimizer & LR:** Adam with adaptive learning rate led to smoother convergence.
- **XGBoost Superiority:** Boosted trees handled imbalance better and captured interactions efficiently.

---

## 🛠️ Future Improvements

- Perform hyperparameter optimization (e.g., grid/random search)
- Explore stacking or ensemble methods (e.g., XGBoost + MLP)
- Use techniques like SHAP for interpretability
- Experiment with class weighting or SMOTE for imbalance handling

---

## 📚 Reference
This project draws inspiration from the [Higgs Boson Machine Learning Challenge](https://www.kaggle.com/competitions/higgs-boson), a competition hosted by CERN and ATLAS on Kaggle.

