# 🏡 King County House Price Prediction – Python Version

Ciao! 👋 This is my personal **Machine Learning** project, originally born from a university course where we didn’t use Python.  
I decided to **rebuild the entire pipeline in Python** to deepen my understanding of the process.  

Compared to the original KNIME version, this Python implementation adds several new components and improvements.  
The aim here is not to achieve *state-of-the-art* performance, but to build a **clear, robust, and reusable pipeline** — something that can serve as a solid base for future projects.

---

## 🚀 Goal
The primary goal was to create a **clean and modular pipeline** that is:
- Easy to understand
- Reusable for other regression tasks
- Flexible enough to adapt to new data

---

## 📋 Project Scope
This repository contains the **full machine learning workflow**, from raw data exploration to final model evaluation and interpretation, including:

### 🔍 Data Exploration & Preprocessing
- In-depth **EDA** (Exploratory Data Analysis)
- **Feature engineering**: creation of new variables (and clustering)  
- **Feature transformation**: handling skewness, scaling, and encoding

### 🏗️ Modeling Workflow
- **Baseline model**: Linear Regression with **ElasticNet-based** feature selection  
- **Non-linear models**: RFECV feature selection using Random Forest importance  
- **1-SE rule** to simplify selected feature sets without hurting performance

### 🤖 Models Implemented
- **Random Forest**
- **Histogram Gradient Boosting**
- **XGBoost**
- **LightGBM**
- **MLP Neural Network**
- **Stacking Model** -> combining XGBoost & Random Forest, with Ridge Regression as the meta-model

### 📊 Evaluation & Insights
- Full performance comparison using **MAE** and other metrics  
- **Residual analysis** with visual diagnostics and confidence interval 
- **SHAP analysis** for XGBoost interpretability

---

## 📦 Dataset
The project uses the [**House Sales in King County, USA** dataset](https://www.kaggle.com/datasets/harlfoxem/housesalesprediction) from Kaggle.  

---

## 🗂️ Repository Structure
- `ML_python.ipynb/` -> Jupyter notebooks for data exploration, preprocessing, and modeling
- `Data/` -> X_train and test & X_train and test after feature selection

- ## 📬 Contact
Since i cannot the training results on Github, if you need those, message me!

