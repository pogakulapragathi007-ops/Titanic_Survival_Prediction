#Titanic Survival Prediction using Machine Learning

#Project Overview

The Titanic Survival Prediction project aims to predict whether a passenger survived the Titanic disaster based on various passenger attributes such as age, gender, passenger class, fare, family information, and embarkation details.

This project demonstrates a complete Machine Learning workflow, including data preprocessing, feature engineering, handling missing values, model training, model evaluation, explainability, model saving, and inference.

The project was developed using Python and Scikit-learn and uses a Random Forest Classifier for prediction.

---

#Problem Statement

The sinking of the RMS Titanic is one of the most well-known maritime disasters in history. Given passenger information, the objective is to build a machine learning model that can predict whether a passenger survived or not.

Target Variable:

- Survived
  - 1 = Survived
  - 0 = Did Not Survive

---

#Dataset Description

The dataset contains passenger information including:

Feature| Description
PassengerId| Unique passenger identifier
Pclass| Passenger class
Name| Passenger name
Sex| Gender
Age| Age of passenger
SibSp| Number of siblings/spouses aboard
Parch| Number of parents/children aboard
Ticket| Ticket number
Fare| Ticket fare
Cabin| Cabin number
Embarked| Port of embarkation
Survived| Survival status

---

#Feature Engineering

To improve model performance, additional features were created from the original dataset.

1. Title Extraction

Passenger titles were extracted from the Name column.

Examples:

- Mr
- Mrs
- Miss
- Master
- Rare

These titles often provide information about age, gender, and social status.

2. Family Size

A new feature named FamilySize was created.

Formula:

FamilySize = SibSp + Parch + 1

This feature represents the total family members traveling together.

3. Cabin Presence

A new binary feature called CabinPresent was created.

- 1 = Cabin information available
- 0 = Cabin information missing

This feature captures whether cabin details exist without requiring the full cabin number.

---

#Data Preprocessing

Handling Missing Values

Missing values were handled using the following strategy:

Age

Missing Age values were replaced using the median age.

Embarked

Missing Embarked values were replaced using the most frequent value (mode).

Cabin

Instead of filling Cabin values, a new CabinPresent feature was created and the original Cabin column was removed.

---

#Encoding Categorical Variables

Machine learning algorithms require numerical input.

The following categorical columns were encoded:

- Sex
- Embarked
- Title

Label Encoding was used to convert text values into numerical values.

---

#Model Selection

The Random Forest Classifier was selected because:

- Handles both numerical and categorical features well
- Robust against overfitting
- Provides feature importance scores
- Works effectively on tabular datasets

---

#-Test Split

The dataset was divided into:

- 80% Training Data
- 20% Testing Data

Random state was fixed to ensure reproducibility.

---

#Model Evaluation

The model was evaluated using:

Accuracy Score

Measures overall prediction accuracy.

Classification Report

Provides:

- Precision
- Recall
- F1-Score

Confusion Matrix

Shows the distribution of:

- True Positives
- True Negatives
- False Positives
- False Negatives

---

#Model Explainability

Feature Importance analysis was used to understand which features contributed most to the prediction.

Commonly important features include:

- Sex
- Fare
- Age
- Pclass
- FamilySize
- Title

This improves model transparency and interpretability.

---

#Model Saving

The trained model was saved using Joblib.

Saved file:

titanic_model.pkl

This allows the model to be reused without retraining.

---

#Inference Example

Example passenger:

- Passenger Class: 1
- Age: 30
- Gender: Female
- Fare: 80
- Family Size: 2

The model predicts whether the passenger would survive.

Example Output:

Prediction: 1

Meaning:

1 = Survived

0 = Did Not Survive

---

#Project Structure

Titanic-Survival-Prediction/

├── data/

│   └── titanic.csv

├── models/

│   └── titanic_model.pkl

├── report/

│   └── Titanic_Project_Report.pdf

├── Titanic_Prediction.ipynb

├── README.md

├── requirements.txt

└── .gitignore

---

#Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- Joblib
- SHAP (optional)

---

#Future Improvements

- Hyperparameter tuning
- Cross-validation
- Deployment using Streamlit
- SHAP visualizations
- Comparison with multiple machine learning algorithms

---

#Conclusion

This project successfully demonstrates a complete machine learning pipeline for Titanic Survival Prediction. The workflow includes data preprocessing, feature engineering, model training, evaluation, explainability, model persistence, and inference. The Random Forest Classifier achieved reliable performance and provides a strong foundation for future improvements and deployment.
