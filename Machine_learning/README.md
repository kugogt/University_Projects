# 🏡 House Price Prediction – Machine Learning Pipeline in KNIME

This project addresses a **supervised machine learning** task: predicting house prices using the  
**"House Sales in King County, USA"** dataset from [Kaggle](https://www.kaggle.com/datasets/harlfoxem/housesalesprediction).  

The entire workflow was developed in **KNIME**, and the repository includes **images of the pipeline**.  
*The KNIME file is available upon request.*

---

💡 If you’re interested in my **Python implementation** of this project, you can find it here:  
[📄 `Personal_Project/ML_python.ipynb`](https://github.com/kugogt/Housing-Price-Prediction)

---

### ⚙️ Workflow Overview

The pipeline is structured into several stages, each handling a key aspect of the machine learning process:

#### 🧪 Feature Engineering
- Creation of new variables (e.g., house age, volume of the house)
- Handling and removal of extreme values and outliers

#### 🔁 Variable Transformation
- Log transformation of skewed numerical features
- Target encoding of the **ZIP code** variable based on average house prices

#### 🎯 Feature Selection
- A **Random Forest–based** feature selection for non-linear models  
- A dedicated **feature selection process** for Linear Regression

#### 🤖 Model Training
Multiple models were trained and compared:
- **Linear Regression** (with its own feature selection strategy)
- **Random Forest**
- **Gradient Boosting** ⬅️ *Best model with MAE = $66,549 on test set*
- **Polynomial Regression**
- **Neural Network** (trained with **Rprop** optimizer)

Each model is highlighted within **yellow blocks** in the KNIME workflow.

---

### 🧪 Experimental Comparison: Linear Regression Variants

To understand the individual impact of preprocessing steps, we ran multiple versions of **Linear Regression** as a fast and interpretable baseline. These are visually separated using **red blocks** in the workflow:

- 📉 **No log transformation**
- 🚫 **No log transformation + no feature engineering**
- ❌ **No log transformation + no feature engineering + no feature selection**

This analysis shows how each step contributes to the model’s predictive performance.

---

### 📬 Contact
If you're interested in the KNIME workflow, feel free to [reach out](lamiaeamilchemetterò) for access to the `.knwf` file.
