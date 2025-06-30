# lastic_Pollution_Classification2
A machine learning project using Logistic Regression to classify rivers as high or low plastic polluters. Based on data from The Ocean Cleanup, the model uses environmental features like rainfall and watershed area. Includes data cleaning, scaling, modeling, evaluation, and feature importance

This project aims to classify countries into **high** or **low** contributors to river plastic pollution using **Logistic Regression**, based on environmental, geographical, and pollution-related features.

---

## 🎯 Project Goal
To build a machine learning model that predicts whether a country is a high or low plastic pollution contributor, using country-level metrics such as area, rainfall, coastline length, and plastic waste data.

---

## 📁 Dataset
- Source: Uploaded via [Google Drive](https://drive.google.com/file/d/1zIk9JOdJEu9YF7Xuv2C8f2Q8ySfG3nHd)
- Format: CSV
- Contains metrics like:
  - Area (km²)
  - Coastline length
  - Rainfall
  - Plastic waste produced and mismanaged
  - Derived ratios and percentages

---

## ⚙️ Workflow Steps
1. **Data Collection**: Loaded data using `gdown` from Google Drive.
2. **Data Cleaning**:
   - Removed unnecessary columns
   - Handled missing values and non-numeric characters
3. **Feature Engineering**:
   - Converted target column into binary class based on the 75th percentile
4. **Data Preprocessing**:
   - Feature scaling using `StandardScaler`
   - Imputation using `SimpleImputer`
5. **Model Training**:
   - Logistic Regression model used
   - `train_test_split` with `stratify=y` for balanced data split
6. **Evaluation**:
   - Accuracy, Precision, Recall
   - Classification Report
   - Feature Importance Visualization

---

## ✅ Results

| Metric      | Score |
|-------------|-------|
| Accuracy    | ~78%  |
| Precision   | ~81%  |
| Recall      | ~96%  |

> ⚠️ Note: Class imbalance may reduce recall for high-contributing countries. Consider using `class_weight='balanced'`.

---

## 📊 Feature Importance Plot

The model coefficients are visualized to show which features most influence classification decisions. Higher bars mean greater importance.

![Feature Importance Plot](your-plot-image-url-if-you-save-it.png)

---

## 🚀 Getting Started

To run this project in **Google Colab**:

```bash
# Install dependencies
!pip install gdown

# Download CSV
import gdown
gdown.download("https://drive.google.com/uc?id=1zIk9JOdJEu9YF7Xuv2C8f2Q8ySfG3nHd", "plastic_data.csv", quiet=False)
