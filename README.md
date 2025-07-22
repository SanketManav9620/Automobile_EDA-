# Email Campaign Response Prediction

This project aims to help small to medium-sized businesses better target customers by predicting whether marketing emails are **ignored**, **read**, or **acknowledged**, using machine learning.

---

## 📊 Dataset Overview

- **Rows:** 68,353 observations  
- **Features:** 12 (numerical & categorical)  
- **Target Variable:** `Email_Status`  
  - 0: Ignored
  - 1: Read
  - 2: Acknowledged

---

## ⚙️ Data Preprocessing

### 1️⃣ Handling Missing Values
- Used **Mode Imputation** for categorical columns (`Customer_Location`).
- Used **Median Imputation** for numerical columns (`Total_Past_Communications`, `Total_Links`, `Total_Images`).
- This ensures missing data does not distort the model while keeping the data realistic.

### 2️⃣ Handling Outliers
- Applied **IQR Capping** to cap extreme values for numerical features such as:
  - `Subject_Hotness_Score`
  - `Word_Count`
  - `Total_Links`
  - `Total_Images`
- Prevents skew and maintains data integrity.

### 3️⃣ Categorical Encoding
- **One-Hot Encoding** for `Customer_Location`.
- Used existing numeric labels for `Email_Type` and `Time_Email_sent_Category`.

---

## 🤖 Modeling

### Algorithms Implemented
- **Random Forest Classifier** (with and without hyperparameter tuning)
- **XGBoost Classifier** (with hyperparameter tuning)

### Hyperparameter Tuning
- Used **RandomizedSearchCV** for both models.
- Improved model performance by finding the best combination of parameters (e.g., `n_estimators`, `max_depth`, `learning_rate` for XGBoost).

---

## 📈 Evaluation

- **Metrics Used:** Accuracy, Precision,
