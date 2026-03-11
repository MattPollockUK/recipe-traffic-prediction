# recipe-traffic-prediction
Predict high-traffic recipes using machine learning (logistic regression &amp; decision tree)
# Recipe Traffic Prediction

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MattPollockUK/recipe-traffic-prediction/blob/main/notebooks/Recipe_Traffic.ipynb)

**Author:** Matt Pollock  
**Date:** September 2025  

## Project Overview
This project predicts **high-traffic recipes** on a recipe website using machine learning. The goal is to identify which recipes are likely to get the most engagement, helping content and marketing teams focus on high-performing recipes.

**Techniques Used:**
- Data cleaning & preprocessing
- Feature encoding and scaling
- Logistic Regression (baseline model)
- Decision Tree Classifier (tuned for recall)
- Model evaluation using accuracy, recall, and ROC AUC

---

## Dataset
- Source: `recipe_site_traffic_2212.csv`  
- Rows: 892  
- Key columns:  
  - `category` – Recipe category (e.g., Vegetable, Pork, Breakfast)  
  - `calories`, `protein`, `carbohydrate`, `sugar`, `servings` – Recipe features  
  - `high_traffic` – Target variable: 1 = High, 0 = Low traffic  

**Data Cleaning Steps:**
- Stripped whitespace from categories  
- Converted `high_traffic` to binary (1 = High, 0 = Low)  
- Converted `servings` to numeric and dropped missing values  

---

## Exploratory Data Analysis (EDA)
- Class balance of high vs low traffic recipes  
- Distribution of recipe features (calories, protein, etc.)  
- Category counts and high-traffic proportions  
- Visualized with histograms, bar charts, and traffic proportion plots  

---

## Modeling & Results
**Logistic Regression (Baseline)**  
- Accuracy: 79.2%  
- Recall: 80.9% ✅ (meets business KPI)  
- ROC AUC: ~0.86  

**Decision Tree Classifier (Tuned by Depth)**  
- Best depth = 3  
- Accuracy: 78.8%  
- Recall: 88.8% ✅ (higher recall than baseline)  
- Visualizations: Recall/Accuracy vs tree depth, confusion matrix, ROC curve  

**Key Metrics:**  
- Recall prioritized to avoid missing high-traffic recipes  
- Confusion matrix and ROC curve help assess performance  

---

## Insights & Recommendations
- High-traffic recipes often come from categories like **Pork, Potato, One Dish Meal, Chicken**  
- Top recipes tend to have **higher calories**  
- Focus content strategy on high-performing categories to increase user engagement  

---

## How to Run
```bash
# Install dependencies
pip install -r requirements.txt

# Open notebook
jupyter notebook notebooks/Recipe_Traffic.ipynb

recipe-traffic-prediction/
├── notebooks/
│   └── Recipe_Traffic.ipynb
├── README.md
├── requirements.txt
└── LICENSE

Tools & libraries
Python 3.x
Pandas, NumPy
Matplotlib
Scikit-learn

This project is licensed under the MIT License.


