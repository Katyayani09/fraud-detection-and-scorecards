# 🌟 Fraud Detection using Credit Card Transaction Data

This repository demonstrates a comprehensive workflow for detecting fraud in credit card transactions using machine learning techniques. The project includes exploratory data analysis, feature engineering, handling imbalanced datasets, and building predictive models like Logistic Regression and Random Forest.

---

## 📋 Table of Contents
- [📌 Project Overview](#project-overview)
- [📂 Dataset Description](#dataset-description)
- [📊 Exploratory Data Analysis](#exploratory-data-analysis)
- [🔧 Feature Engineering](#feature-engineering)
- [⚖️ Handling Imbalanced Data](#handling-imbalanced-data)
- [🤖 Modeling](#modeling)
  - [📈 Logistic Regression](#logistic-regression)
  - [🌲 Random Forest](#random-forest)
- [✅ Conclusion](#conclusion)
- [▶️ Requirements ](#requirements)
- [📦 Dependencies](#dependencies)

---

## 📌 Project Overview
The goal of this project is to identify fraudulent credit card transactions using a dataset of real-world transaction records. Machine learning models are employed to classify transactions as fraud or non-fraud, with a particular focus on balancing the trade-off between precision and recall.

---

## 📂 Dataset Description
The dataset includes information on transactions such as:
- 💰 Transaction amount (`amt`)
- 🕒 Transaction time (`trans_date_trans_time`)
- 📍 Merchant details 
- 👤 User details (age, gender, zip code, etc.)
- 🛡️ Fraud labels (`is_fraud` - 1 indicates fraud, 0 indicates non-fraud)

---

## 📊 Exploratory Data Analysis
### 📈 Univariate Analysis
Violin plots and histograms were used to analyze the distribution of features like 📅 Age, 🕑 Hour of the day, 💵 Transaction amount
- ⏰ Fraud transactions are more frequent during certain hours of the day.
- 👨‍👩‍👦 Certain age groups exhibit higher fraud rates.

### 📉 Bivariate Analysis
Relationships between features and the target variable were explored:
1. **👥 Gender Distribution**: Fraudulent transactions are skewed by gender.
2. **📊 Fraud Trends Over Time**: Seasonal patterns and spikes in fraud.
3. **🏬 Merchant Categories**: Some categories have disproportionately high fraud rates.

---

## 🔧 Feature Engineering
The following transformations were applied:
- 📆 Extracted `hour`, `day`, and `month` from the transaction timestamp.
- 🛣️ Calculated the distance between cardholder and merchant (`dist`).
- 🏙️ Binned city populations into groups (`<5k`, `5k-50k`, etc.).

---

## ⚖️ Handling Imbalanced Data
The dataset exhibited severe class imbalance (fraud cases <1%). **Synthetic Minority Oversampling Technique (SMOTE)** was used to generate synthetic samples for the minority class, ensuring a balanced dataset for training.

---

## 🤖 Modeling
### 📈 Logistic Regression
**Performance**:
- ✅ Precision: ~0.05
- ✅ Recall: ~0.75
- ✅ F1-Score: ~0.10

The logistic regression model struggled due to the imbalanced nature of the dataset.

### 🌲 Random Forest
**Performance**:
- 🌟 Precision: 0.88
- 🌟 Recall: 0.73
- 🌟 F1-Score: 0.80

Random Forest significantly outperformed Logistic Regression, achieving high precision and a balanced F1-Score. It demonstrated robustness in detecting fraudulent transactions.

---

## ✅ Conclusion
1. 🌲 **Random Forest** emerged as the preferred model for fraud detection due to its higher precision and F1-score.
2. 🛠️ Fine-tuning thresholds or exploring ensemble methods can further optimize performance.

---

## ▶️ Requirements
1. Clone this repository:

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Place the dataset (`fraudTrain.csv`, `fraudTest.csv`) in the `data/` directory.
4. Run the analysis script:
   ```bash
   python analysis.py
   ```
---

## 📦 Dependencies
- 🐍 Python 3.7+
- 📊 pandas
- 🔢 numpy
- 📉 matplotlib
- 🎨 seaborn
- 🧠 scikit-learn
- ⚖️ imbalanced-learn
---
