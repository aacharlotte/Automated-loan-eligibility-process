# Automated Loan Eligibility Process
The aim of this project is to build a model that can identify customers eligible for the loan amount they have applied for, so that they can be specifically targeted to move forward with loan processing.  


### Tools and Libraries Used
- **Pandas**: Data manipulation
- **NumPy**: Numerical computations  
- **Seaborn**: Data visualization  
- **Matplotlib**: Plotting and customization

---

## Problem Statement and Aim of the Project
Company X deals in all home loans. They have a presence across all urban, semi-urban, and rural areas. A customer applies for a home loan, and then the company validates the customer's eligibility for a loan.

The company wants to automate the loan eligibility process (real-time) based on customer details provided while filling the online application form. These details are gender, marital status, education, number of dependents, income, loan amount, credit history, and others.

To automate this process, the aim of this project is to build a model that can identify the customer's segments, those eligible for the loan amount they have applied for, so that they can be specifically targeted to move forward with loan processing.

---

## Skills and Concepts Demonstrated
- EDA  
- Preprocessing
- Train-test split
- Building a default and tuned DecisionTreeClassifier, SVC and RandomForestClassifier
- Interpreting model performance including strengths and weaknesses of models in terms of achieving the project aim

---

## Visualizations and Interpretation

### Default Decision Tree
<img src="https://github.com/aacharlotte/Automated-loan-eligibility-process/blob/main/Default%20Decision%20Tree.png" width="50%" />

**Key Observations:**
- The default decision tree model performs not so well in identifying eligible loan applicants. Even though the precision is not so bad (81%), a recall of 79% implies that about 21% of the real eligible loan applicants were missed by the model. Hence, using a default decision tree would not be ideal for this project.

---

### Tuned Decision Tree
<img src="https://github.com/aacharlotte/Automated-loan-eligibility-process/blob/main/Tuned%20Decision%20Tree.png" width="80%" />

**Key Observations:**
- The tuned decision tree model performs well in identifying Loan status Y, making it highly sensitive to those approved for loans with a precision of 82%, recall of 100%, and F1 score of 90%. Even though the precision for N (those not eligible for loan) is 100%, even after hyperparameter tuning, the model correctly catches only about half of those not approved loans, missing the rest. 
  
---

### Support Vector Machine 
<img src="https://github.com/aacharlotte/Automated-loan-eligibility-process/blob/main/SMV.png" width="50%" />

**Key Observations:**
- The support vector classifier (SVC) model performs very well detecting real loan status Y cases (those eligible for loan) with a recall of 100% but performs extremely poorly in identifying those that are not eligible for loan (with 0% precision, recall, and f1-score).  

---

### Default Random Forest
<img src="https://github.com/aacharlotte/Automated-loan-eligibility-process/blob/main/Default%20Random%20Forest.png" width="50%" />

**Key Observations:**
- Like the tuned decision tree, the random forest model performs well in identifying those eligible for the loan applied for.
  
---

### Tuned Random Forest
<img src="https://github.com/aacharlotte/Automated-loan-eligibility-process/blob/main/Tuned%20Random%20forest.png" width="50%" />

**Key Observations:**
- Results for the tuned random forest model are exactly the same as those of the SVC. Even though the recall is 100%, the precision of 68% while predicting those eligible of a loan is relatively low. Also, missing all those not eligible for a loan (recall of 0% for class N) indicates that all those not eligible for a loan were wrongly predicted as eligible. This would be misleading. Since the model never predicts those not eligible for a loan, these would be targeted for loan processing yet they souldn't be. 

---
**Conclusion**

- A tuned decision tree model, with 100% recall and recision of 82% for loan eligible cases is more efficient in identifying customers eligible for the loan amount they have applied for. This would aid proper targeting.
  
---

## Author & License
**Author**: [Charlotte Arinaitwe]  
**Date**: 2025  
**License**: MIT

---
