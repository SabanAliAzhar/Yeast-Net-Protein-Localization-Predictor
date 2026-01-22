# Yeast-Net-Protein-Localization-Predictor
A PyTorch-based Deep Learning project that classifies yeast protein localization sites. The project specifically explores the impact of Dropout and L2 Regularization (Weight Decay) on model generalization and training stability.

# Yeast-Net: Protein Localization Predictor

This repository implements a Multi-Layer Perceptron (MLP) using **PyTorch** to predict the cellular localization sites of proteins based on the [UCI Yeast Dataset](https://archive.ics.uci.edu/dataset/110/yeast). 

The primary focus of this project is to demonstrate and compare different **regularization techniques** to prevent overfitting in deep learning models.

## 📊 Dataset Overview
The dataset contains information about various protein sequences and their corresponding localization sites (e.g., Cytoplasmic, Mitochondrial, Nuclear, etc.).
- **Features:** 8 predictive attributes (amino acid sequence content).
- **Classes:** 10 localization sites.
- **Instances:** 1,484.

## 🧠 Model Architectures
We compare four distinct training scenarios:
1. **Baseline MLP:** No regularization.
2. **Dropout Model:** Includes a Dropout layer ($p=0.5$) to randomly deactivate neurons during training.
3. **L2 Regularization:** Implemented via `weight_decay` in the Adam optimizer.
4. **Hybrid Model:** Combining both Dropout and L2 Regularization for maximum stability.



## 🚀 Key Features
- **Data Preprocessing:** Includes `LabelEncoding` for targets and `StandardScaling` for features.
- **Data Splitting:** Implements a Train/Validation/Test split (70/15/15) with stratification to handle class imbalance.
- **Visualization:** Comparative loss curves for all four regularization strategies and a Confusion Matrix for final evaluation.

## 📈 Results & Comparison
The project generates a 2x2 comparison plot to visualize how different strategies affect the gap between Training and Validation loss.

| Strategy | Purpose | Key Observation |
| :--- | :--- | :--- |
| **Baseline** | Standard Training | High risk of overfitting. |
| **Dropout** | Robustness | Reduces reliance on specific neurons. |
| **L2 Reg** | Weight Control | Penalizes large weights to simplify the model. |
| **Hybrid** | Optimization | Most stable convergence across epochs. |



