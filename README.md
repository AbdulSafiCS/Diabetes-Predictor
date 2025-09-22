#  Diabetes Prediction Using Health Indicators

Diabetes is one of the leading chronic health conditions globally, posing a significant challenge for healthcare systems. Early diagnosis and effective prediction models can help manage and mitigate complications arising from diabetes. This project aims to build a predictive model using statistical methods and machine learning algorithms on a real-world dataset from the UCI Machine Learning Repository.

We performed a comprehensive data analysis pipeline that includes statistical exploration, preprocessing, feature selection, dimensionality reduction, and classification modeling. Our objective was to understand the relationships between various health indicators and the presence of diabetes, and to develop a reliable model that can predict the likelihood of a person having diabetes based on health survey data.

The dataset used in this project is the CDC Diabetes Health Indicators Dataset (UCI Dataset ID: 891). This dataset includes survey data collected from U.S. adults, focusing on behavioral and health indicators associated with diabetes risk.

The dataset contains 21 features which include:
1. Demographic features: Sex, Age, Education, Income
2. Behavioral features: Smoking, AlcoholDrinking, PhysicalActivity
3. Health conditions: BMI, Stroke, PhysicalHealth, MentalHealth, SleepTime
4. Chronic diseases and indicators: HighBP, HighChol, Asthma, KidneyDisease, SkinCancer
5. Target: Diabetes_binary: Binary classification label where 1 indicates the individual is diabetic and 0 indicates non-diabetic.

---

##  Dataset  
- **Source:** CDC Diabetes Health Indicators Dataset ([UCI Repository](https://archive.ics.uci.edu/dataset/891/cdc+diabetes+health+indicators))  
- **Features:** 21 demographic, behavioral, and health condition variables (Age, BMI, Smoking, Physical Activity, HighBP, etc.)  
- **Target:** `Diabetes_binary` (1 = diabetic, 0 = non-diabetic)  

---

## Project Workflow  

### 1. Exploratory Data Analysis (EDA)  
- Computed **central tendency, skewness, and correlations** across features.  
- Created visualizations (heatmaps, histograms) to identify trends and anomalies.  
- Addressed **class imbalance** between diabetic vs. non-diabetic samples.  

### 2. Data Preprocessing  
- **Encoding:** Converted binary categorical variables to numeric form.  
- **Scaling:** Used MinMaxScaler to normalize features to [0,1].  
- **Feature Selection:** Applied Chi-Squared test (SelectKBest).  
- **Dimensionality Reduction:** Performed PCA for visualization and model simplification.  

### 3. Model Building  
Tested three main classifiers in both standard and **class-balanced** versions:  
- Logistic Regression  
- Random Forest Classifier  
- XGBoost Classifier  

Each model was trained on an 80/20 train-test split, stratified by the target variable.  

---

## Models Used  

| Model                    | Accuracy | Precision | Recall | F1-Score | Notes                          |  
|--------------------------|----------|-----------|--------|-----------|--------------------------------|  
| Logistic Regression       | 0.77     | 0.76      | 0.79   | 0.77      | Baseline model                |  
| Random Forest             | 0.81     | 0.80      | 0.82   | 0.81      | Good feature importance insight |  
| XGBoost                   | 0.84     | 0.85      | 0.83   | 0.84      | Best-performing model          |  

Balanced versions improved **recall for diabetic cases**, which is critical in healthcare settings.  

---

## Deployment Plan  
- **Web App:** Create a lightweight front end using Flask or Streamlit.  
- **Cloud Hosting:** Deploy to AWS or Heroku for public access.  
- **User Input:** Allow healthcare professionals or patients to input health indicators and receive instant predictions.  
- **Monitoring:** Implement continuous monitoring and auto-retraining with new data.  
- **Integration:** Connect with Electronic Health Record (EHR) systems for real-world clinical use.  

---

## Key Learnings  
- **Handling Imbalanced Data:** Class weights and evaluation metrics like F1-score and ROC-AUC are essential.  
- **Feature Engineering:** Scaling, encoding, and PCA dramatically improve model performance and interpretability.  
- **Model Comparison:** Testing multiple models reveals trade-offs between precision and recall, which is especially important in healthcare contexts.  

---

## Future Work  
- Implement **SMOTE** or advanced resampling for better minority-class recall.  
- Incorporate **temporal health data** to predict trends over time.  
- Build an **interactive web/mobile app** to improve accessibility.  
- Experiment with **deep learning** and **explainability tools** (e.g., SHAP, LIME) to enhance transparency in predictions.  

---

## References  
- [CDC Diabetes Health Indicators Dataset – UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/891/cdc+diabetes+health+indicators)  
- [Kaggle Dataset](https://www.kaggle.com/datasets/alexteboul/diabetes-health-indicators-dataset)  
- [Scikit-learn Documentation](https://scikit-learn.org/)  
- [CRISP-DM Methodology](https://www.datascience-pm.com/crisp-dm-2/)  
- [Random Forest, XGBoost Guide](https://medium.com/@brandon93.w/decision-tree-random-forest-and-xgboost-an-exploration-into-the-heart-of-machine-learning-90dc212f4948)  

---

## Authors  
- **Abdul Hasib Safi** ([@AbdulSafiCS](https://github.com/AbdulSafiCS))  
- COMP 541 – Data Mining Team  

---

### How to Use This Notebook  
1. Open the notebook in Colab using the badge at the top.  
2. Run all cells to reproduce analysis and model results.  
3. Use the notebook as a base for deployment in a web app or integration with other systems.  
