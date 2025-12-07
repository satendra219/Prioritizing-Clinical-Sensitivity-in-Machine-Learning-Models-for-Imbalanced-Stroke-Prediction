# Prioritizing-Clinical-Sensitivity-in-Machine-Learning-Models-for-Imbalanced-Stroke-Prediction
**Stroke Prediction: Navigating the Accuracy Paradox**

📌Project Overview:

This project focuses on predicting the likelihood of a stroke in patients based on physiological factors like age, glucose levels, and BMI. Using the Kaggle Stroke Prediction Dataset, we trained multiple Machine Learning models to identify high-risk individuals.

The key highlight of this project is the critical analysis of "Accuracy vs. Sensitivity" in imbalanced medical datasets. We demonstrate why a model with 94% accuracy can be dangerous in healthcare and why a model with 75% accuracy might actually be better.

📂 Dataset

*Source: Kaggle Stroke Prediction Dataset

*Records: 5,110 Rows

*Features: 11 (Age, Gender, Hypertension, Heart Disease, BMI, etc.)

*Class Imbalance: Only 4.9% of patients had a stroke, making this a highly imbalanced dataset.

🛠️ Tech Stack

*Language: Python

*Libraries: Pandas, NumPy, Scikit-Learn, Matplotlib, Seaborn

*Techniques: Data Preprocessing, Mean Imputation, Label Encoding, Feature Scaling (StandardScaler), Classification.

📊 Key Findings (The "Accuracy Paradox")

We trained four models: Logistic Regression, Decision Tree, Random Forest, and K-Nearest Neighbors (KNN).

At first glance, KNN and Random Forest looked like the winners with ~94% accuracy. However, a deeper dive into the Confusion Matrix revealed a critical flaw:

Model-------------------Accuracy--Recall(Sensitivity)-------------Verdict

KNN______________________93.93%__________0.00____________❌ Failed to detect any stroke patients.

Random Forest___________93.83%__________0.00____________❌ Biased towards the majority class.

Decision Tree____________92.07%__________0.15____________⚠️ Poor sensitivity.

Logistic Regression______74.95%__________0.76____________✅ WINNER: Identified 76% of stroke cases.

💡 Conclusion

In medical diagnostics, False Negatives (telling a sick patient they are fine) are fatal.

KNN & Random Forest achieved high accuracy by simply predicting "No Stroke" for everyone.

Logistic Regression (with balanced class weights) sacrificed overall accuracy to prioritize Recall, successfully flagging high-risk patients.

Therefore, Logistic Regression is the most clinically viable model for this specific dataset.

📈 Visualizations

1. Confusion Matrix Comparison: Left: KNN (High Accuracy, Zero Recall) | Right: Logistic Regression (High Recall)

2. Class Imbalance: Only 4.9% of the data represents stroke cases.

👨‍💻 Author:Satendra Yadav
