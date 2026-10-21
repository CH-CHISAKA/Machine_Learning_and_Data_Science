# Kaggle Titanic Challenge: Machine Learning from Disaster

This repository contains the solution pipeline for the classic **Kaggle Titanic: Machine Learning from Disaster** competition. The objective is to predict passenger survival using demographic, socio-economic, and ticketing data.

## 🚀 Project Goals
* **Model Exploration:** Implement and evaluate baseline **Logistic Regression** and **Ensemble Methods** (e.g., Random Forests).
* **Kaggle Deployment:** Format, export, and submit predictions matching the strict Kaggle submission template.
* **Portfolio Development:** Establish verified participation in competitive data science challenges for CV optimization.

## 📋 Deliverables
* **Kaggle Username:** [siredwardchisaka]
* **Source Code:** Core pipeline steps available in the main notebook/script file.

## ⚙️ Project Scope & Boundaries

### In Scope
* **Data Preprocessing:** Handling missing data in core columns (`Age`, `Embarked`, `Fare`).
* **Feature Engineering:** Basic transformations, encoding categorical variables (`Sex`, `Embarked`), and feature scaling.
* **Model Training:** Training a baseline Logistic Regression model and a benchmark Ensemble classifier.
* **Submission Pipeline:** Generating a compliant `submission.csv` containing exactly 418 rows with `PassengerId` and `Survived` columns.

### 🚫 Out of Scope
* **Hyperparameter Tuning:** No exhaustive grid searches (`GridSearchCV`), randomized searches, or automated Bayesian optimization framework tuning are performed. Models utilize default or basic heuristic parameters to focus strictly on structural pipeline implementation.
* **Advanced Feature Engineering:** Complex extractions, such as parsing ticket prefix frequencies, tracking multi-generation family survival groups, or cross-referencing external historical passenger manifests, are excluded.
* **Deep Learning Frameworks:** Implementation is limited to traditional tabular machine learning methods; neural networks (such as PyTorch or TensorFlow architectures) are not utilized.