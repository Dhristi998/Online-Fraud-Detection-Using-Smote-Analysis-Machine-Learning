## 🔐 Online Fraud Detection using SMOTE & Random Forest

This project tackles the challenge of detecting fraudulent transactions in online financial systems using machine learning. Due to the highly **imbalanced nature** of fraud datasets—where genuine transactions far outnumber fraudulent ones—traditional models often fail to identify fraud effectively.

To address this, we combined **SMOTE (Synthetic Minority Oversampling Technique)** with a **Random Forest Classifier** to enhance fraud detection by synthetically balancing the dataset and improving model recall. Our pipeline includes data preprocessing, PCA-based dimensionality reduction, SMOTE balancing, model training, and evaluation using recall, precision, F1-score, and ROC-AUC.

---

## 🧠 Dataset and PCA Explanation

The dataset used is derived from the publicly available [Kaggle Credit Card Fraud Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud), containing anonymized transaction records with highly sensitive user and transaction data.

To protect data privacy and reduce dimensionality, **Principal Component Analysis (PCA)** was applied to the original features. PCA transforms the original variables into a set of linearly uncorrelated components that retain most of the dataset’s variance. This transformation helps in:

- **Anonymizing sensitive transaction attributes**  
- **Reducing noise and redundant information**  
- **Speeding up model training and improving generalization**  

Only the `Time`, `Amount`, and `Class` features remain in their original form—while the rest of the features (`V1` to `V28`) are the principal components obtained through PCA.

---

## ⚙️ Methodology

1. **Data Preprocessing**
   - Handled missing values and scaled features.
   - Performed PCA (pre-applied in the dataset) to ensure dimensionality reduction and anonymity.

2. **SMOTE Balancing**
   - SMOTE was applied *only to the training data* to synthetically generate minority (fraudulent) samples and balance the dataset.

3. **Model Training**
   - Trained using Random Forest Classifier.
   - Compared performance with and without SMOTE.

4. **Evaluation Metrics**
   - **Without SMOTE**: High accuracy but low recall for fraud cases.
   - **With SMOTE**: Improved recall and F1-score, indicating better fraud detection capabilities.

---

## 📈 Results (Key Metrics)

| Metric              | Without SMOTE | With SMOTE  |
|---------------------|---------------|-------------|
| Accuracy            | 98.7%         | 96.5%       |
| Precision (Fraud)   | 71%           | 65%         |
| Recall (Fraud)      | 12%           | 81%         |
| F1-Score (Fraud)    | 20%           | 72%         |
| ROC-AUC             | 0.84          | 0.93        |

---

## ✅ Why Random Forest + SMOTE?

- Random Forest is robust, interpretable, and performs well with both linear and non-linear features.
- SMOTE drastically improves recall, which is **crucial in fraud detection**, where false negatives can result in major financial loss.

---

## 🛠️ Future Enhancements

- Incorporate time-based, behavioral, and geolocation features.
- Explore deep learning models like RNNs and Autoencoders.
- Deploy as a real-time API for production-level fraud detection.

---
