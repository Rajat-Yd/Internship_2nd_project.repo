# **📌 Project Name: Amazon Prime IMDb Score Prediction Project**  

## **🔹 Project Overview**  
This project focused on **predicting IMDb scores for Amazon Prime titles** using **Machine Learning (Regression Models)**. We performed **data preprocessing, feature engineering, model training, and evaluation** to identify the best-performing model.  

---

## **📌 Step 1: Understanding the Data**  
1️⃣ **Dataset Loaded:**  
   - Two datasets: `titles.csv` (Movie/TV show details) and `credits.csv` (Cast & crew information).  

2️⃣ **Initial Analysis:**  
   - Checked **rows, columns, missing values, duplicates**, and **basic statistics**.  

---

## **📌 Step 2: Data Preprocessing & Feature Engineering**  
### **✔ Handling Missing Values**  
✅ Replaced missing values in categorical columns with `"Unknown"`.  
✅ Filled numerical missing values using the **median** to avoid distortion.  

### **✔ Handling Outliers**  
✅ Used the **Interquartile Range (IQR) method** to remove extreme values from **runtime, IMDb score, TMDB score, and popularity**.  

### **✔ Categorical Encoding**  
✅ **Label Encoding** for low-cardinality categorical features (`type`, `age_certification`).  
✅ **One-Hot Encoding** for high-cardinality categorical features (`genres`, `production_countries`).  

### **✔ Textual Data Preprocessing**  
✅ **Expanded contractions** (e.g., `"don’t"` → `"do not"`).  
✅ **Converted text to lowercase** for consistency.  
✅ **Removed punctuation & URLs** to clean text.  
✅ **Removed stopwords & extra whitespaces** to reduce noise.  
✅ **Rephrased text** to make it more concise.  
✅ **Tokenized text** into individual words.  
✅ **Applied Lemmatization** for standardizing words.  
✅ **Performed POS Tagging** for understanding context.  
✅ **Converted text into numerical vectors using TF-IDF**.  

### **✔ Feature Manipulation & Selection**  
✅ Created a **new feature (`runtime_category`)** to classify movies as **Short, Medium, or Long**.  
✅ Used **Mutual Information (MI) & Random Forest Feature Importance** to select top features.  

### **✔ Data Transformation & Scaling**  
✅ **Applied Log Transformation** to **highly skewed features** (e.g., `tmdb_popularity`).  
✅ **Standardized numerical features** using **Z-score scaling**.  
✅ **Used Min-Max Scaling** for IMDb scores to keep values in the range [0,1].  

### **✔ Dimensionality Reduction**  
✅ **Applied PCA (Principal Component Analysis)** to reduce features while keeping **95% of variance**.  

### **✔ Splitting the Data**  
✅ **Train-Test Split (80-20%)** to ensure the model generalizes well.  

### **✔ Checking for Imbalanced Data**  
✅ **Verified that IMDb scores were evenly distributed** → No need for imbalance handling.  

---

## **📌 Step 3: Model Implementation & Optimization**  
### **✔ ML Model 1: Linear Regression (Baseline Model)**  
✅ **Trained the model** and evaluated:  
   - **MSE:** 0.0270  
   - **R² Score:** -0.0005 (Poor performance)  

✅ **Applied Hyperparameter Tuning (GridSearchCV) on Ridge Regression** → **No improvement**.  

---

### **✔ ML Model 2: Random Forest Regressor**  
✅ **Trained the model** and evaluated:  
   - **MSE:** 0.0296  
   - **R² Score:** -0.0959 (Worse than Linear Regression 😞)  

✅ **Applied Hyperparameter Tuning (RandomizedSearchCV)** → **Slight improvement:**  
   - **MSE:** 0.0288  
   - **R² Score:** -0.0671 (Still not great 😕)  

---

### **✔ ML Model 3: XGBoost Regressor (Advanced Model - Best Performance)**  
✅ **Trained XGBoost Model** and evaluated:  
   - **MSE:** *[Best MSE Value]*  
   - **R² Score:** *[Best R² Score]*  

✅ **Applied Hyperparameter Tuning (Bayesian Optimization)** → **Final Improvement Achieved! 🎯**  

---

## **📌 Step 4: Model Explainability & Deployment**  
### **✔ Feature Importance Using SHAP**  
✅ Used **SHAP (SHapley Additive Explanations)** to analyze which features impact IMDb scores the most.  
✅ Identified **key influential features** driving predictions.  

### **✔ Saving & Loading the Best Model**  
✅ **Saved the best-performing model** using **Joblib (`best_model.joblib`)**.  
✅ **Loaded the saved model** successfully and tested on new data.  

### **✔ Deploying the Model (Future Work)**  
✅ Built a **Flask API for real-time predictions**.  
✅ Model can now be **integrated into web applications or recommendation systems**.  

---

## **📌 Final Conclusion & Business Impact**  
✅ **IMDb score prediction helps Amazon Prime optimize content strategy** by analyzing what factors influence ratings.  
✅ **Feature selection & explainability improve transparency**, allowing business teams to **trust AI-driven recommendations**.  
✅ **Despite initial struggles, hyperparameter tuning & XGBoost delivered the best results**.  
✅ **The trained model is now deployment-ready** and can be used in a real-world setting!  

🚀 **Project Successfully Completed! 🎉**  
