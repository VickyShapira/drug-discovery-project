# drug-discovery-project
# 🧬 Molecular Binding Affinity Prediction

This project focuses on predicting RNA binding affinity (`RNA_28`) for approximately 450,000 molecules based on their chemical structure. A machine learning pipeline was developed to handle large-scale data merging, analysis, modeling, and performance evaluation using stratified subsets.

---

## 📁 Dataset

- **Size**: ~450,000 molecules, split across 8 CSV files  
- **Structure**: Each row represents a unique molecule identified by an ID  
- **Features**: Structural and chemical descriptors  
- **Target**: `RNA_28` — a continuous score indicating RNA binding affinity  
- **Note**: Due to file size limitations, only a **sample subset** is included in this repository for demonstration purposes.

---

## 🧪 Project Workflow

### 🔗 1. Data Merging
- Combined 8 separate CSV files into one unified dataset using `pandas`.

### 📊 2. Exploratory Data Analysis (EDA)
- Analyzed feature and target distributions
- Identified key features correlated with `RNA_28`
- Visualized relationships using `matplotlib` and `seaborn`

### ✂️ 3. Subset Creation
- Created a **stratified 1% subset** to preserve the distribution of important features and target values
- Enabled fast iteration and model development on smaller data samples

### 🤖 4. Modeling
- Trained a **stacked regression model** using selected features  
  - **Base models**:  
    - 🔹 Lasso Regression  
    - 🔹 Elastic Net  
    - 🔹 XGBoost  
    - 🔹 LightGBM  
- Evaluation Metrics:  
  - 📉 **RMSE** (Root Mean Square Error)  
  - 📈 **R² Score**  
- Visualized predicted vs. actual `RNA_28` scores

### 📈 5. Upscaling
- Scaled training from 1% to **5%** of the full dataset
- Re-evaluated model performance at each stage
- Maintained consistent feature engineering and validation strategy

---

## 📈 Results

| Subset | R² Score | RMSE |
|--------|----------|------|
| 5%     | **0.83** | **0.48** |

- Final model trained on 5% of the data achieved strong performance
- Predicted vs. actual scores showed high correlation with minor deviations in edge cases

---

## 🛠 Technologies Used

- **Python**: `pandas`, `numpy`, `xgboost`, `lightgbm`, `matplotlib`, `seaborn`  
- **Development**: Jupyter Notebook  
- **Version Control**: Git & GitHub  
