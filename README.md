# 🔐 Cyberattack Detection & Classification Using Machine Learning

This project presents a machine learning pipeline for detecting and classifying cyberattacks based on real-world network traffic data. The ML model can accurately distinguish between **normal traffic** and **14 different cyberattack types** using supervised learning techniques.

This project presents a complete machine learning pipeline for detecting and classifying cyberattacks using network traffic data, implemented and documented through a detailed Jupyter Notebook and GitHub repository. The workflow includes data preprocessing, visualization, handling class imbalance, training multiple models for binary and multiclass classification, performance evaluation, and hyperparameter tuning—demonstrating an end-to-end approach to building a practical, intelligent intrusion detection system.

---

## 📌 Project Objective

To build a machine learning model that:

- Detects whether incoming network traffic is an attack or normal
- Identifies the **type of cyberattack** in multiclass classification
- Achieves high accuracy and interpretability using real-world features

---

## 📚 Dataset: Edge-IIoTset

- **Source**: [Kaggle – Edge-IIoTset](https://www.kaggle.com/datasets/mohamedamineferrag/edgeiiotset-cyber-security-dataset-of-iot-iiot)
- **Description**: Comprehensive IoT/IIoT dataset for intrusion detection
- **Target Variables**:
  - `Attack_label`: For **binary classification** (0: normal, 1: attack)
  - `Attack_type`: For **multiclass classification** (e.g., DoS, MITM, Malware)
- **Attack Types**: 14 unique types grouped under 5 categories

---

## 🔁 Project Workflow

### 1. **Data Loading & Exploration**
- Loaded CSV dataset and reviewed shape, info, and column distributions
- Reviewed attack label and attack type frequencies

### 2. **Data Cleaning**
- Removed irrelevant columns such as:
  - IP addresses, timestamp fields, raw payloads, HTTP/ARP/MQTT details
- Dropped features with low variance or high redundancy
- Checked for and handled null values

### 3. **Feature Engineering**
- Removed duplicate or non-contributing columns
- Mapped categorical targets to integer labels
- Standardized numeric features for model training

### 4. **Data Visualization**
- Plotted:
  - Distribution of normal vs attack traffic
  - Class imbalance in attack types
  - Heatmaps for feature correlation
- Gained insights into data skewness and class imbalance

### 5. **Class Imbalance Solutions**
- **SMOTE**: Used to oversample minority classes
- **Class Weighting**: Applied in model training (e.g., Random Forest, XGBoost)
- **Threshold Tuning**: Adjusted decision thresholds for better performance

---

## 🤖 Models Implemented

### Binary Classification
- **Logistic Regression**
- **Decision Tree Classifier**
- **Random Forest Classifier** ✅ Best performance (92% accuracy)

### Multiclass Classification
- **Random Forest**
- **XGBoost** ✅ Best multiclass performance (~91% accuracy)
- **MLP**

---

## 🔧 Model Fine-Tuning

- Used **GridSearchCV** and **RandomizedSearchCV** for:
  - `max_depth`, `n_estimators`, `min_samples_split`, `learning_rate`, etc.

---

## 🧪 Evaluation Metrics

Each model was evaluated using:
- **Accuracy**
- **Precision, Recall, F1 Score**
- **Confusion Matrix**
- **ROC AUC Curve**
- **Feature Importance Ranking**

---

## 📊 Results

| Task                   | Best Model     | Accuracy | Notes |
|------------------------|----------------|----------|-------|
| Binary Classification  | Random Forest  | 99%      | Strong on imbalanced data |
| Multiclass Classification | XGBoost     | 89–91%   | Good recall on common attack types |

---

## ⚠️ Known Limitations

- **Rare Attack Types** (e.g., Password, Uploading) had lower recall due to insufficient samples
- Requires tuning when applied to unseen or real-time traffic
- Model is currently trained offline and not integrated into a live environment

---
