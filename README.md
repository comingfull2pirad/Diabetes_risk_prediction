**Project Overview**

This project analyzes pharmacy consultation and health data to help WellData and a large U.S. pharmacy chain understand which attributes of a customer’s record indicate elevated risk of diabetes. The dataset includes 100,000 customer records with demographics, lifestyle indicators, clinical measures (such as blood test results), and a target column called `diabetes` which indicates incidence of the condition.  THis dataset will be used to develop a model to flag diabetes risk.

**Objective**

Use the dataset to model and interpret the target variable `diabetes`, which encodes whether a customer has diabetes. The goal is to design a flagging system for diabetes risk, whose sensitivity can be tuned so that it provides a valuable risk signal to pharmacists and admin staff, while avoiding over‑ or under‑identification of high‑risk customers. 

**Workflow**

The workflow in this notebook will progress from exploratory data analysis (EDA), through preprocessing and feature engineering, and conclude with modelling, model tuning and interpretation. Throughout, the system will be developed with a “human in the loop” mindset so that pharmacists can incorporate model outputs, explanations, and their own judgment when deciding whether to initiate early intervention.

**Data Dictionary for Data file**

    - year: year data was recorded
    - gender: patient's gender
    - age: patient age
    - location: patient's State of residence
    - race: patient's race
    - hypertension: hypertension diagnosis
    - heart_disease: heart_disease diagnosis
    - smoking_history: patient's history of smoking
    - bmi: patient's body Mass Index
    - HbA1c_level: patient's blood glucose HbA1c
    - blood_glucose_level: HbA1c fasting blood glucose 
    - diabetes: diabetes diagnosis - Binary target indicating whether the customer has diabetes


**Evaluation Framework**

Because there is class imbalance in the `diabetes` column, model performance will be evaluated using the F1 score to balance precision and recall on the minority class (ie `diabetes`), as this is the rare and clinically important outcome and missing these cases (false negatives) is much more serious than misclassifying a healthy person as at risk. Additional analysis will include inspection of the confusion matrix and ROC curve, with particular focus on how threshold changes alter the sensitivity of the flagging system and the trade‑off between false positives and false negatives.
