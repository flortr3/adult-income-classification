# Adult Income Classification

A supervised machine learning classification project focused on predicting whether an individual's annual income exceeds $50,000.

The project compares multiple classification algorithms and evaluates the effect of class imbalance using SMOTE.

## Project Objective

The objective was to classify adults into two income categories:

- <= $50K
- > $50K

The project also investigated how class imbalance affects model performance and whether SMOTE improves the ability to identify the minority higher-income class.

## Dataset

The dataset originally contained:

- 48,842 observations
- 15 variables

After duplicate removal:

- 48,790 observations

Target distribution:

- 76.06% <= $50K
- 23.94% > $50K

This imbalance made minority-class performance an important part of the evaluation.

## Data Preprocessing

The workflow included:

- Duplicate removal
- Missing-value handling
- Categorical encoding
- Robust feature scaling
- Stratified train-test split
- Leakage-safe preprocessing
- SMOTE applied only to training data

## Models Compared

Four classification models were evaluated:

- Logistic Regression
- K-Nearest Neighbors
- Decision Tree
- Linear SVM

## Results Before SMOTE

KNN produced the strongest overall ROC-AUC before class balancing.

| Metric | KNN Result |
|---|---:|
| Accuracy | 86.82% |
| ROC-AUC | 0.9213 |
| Recall for > $50K | 65.92% |
| F1-Score for > $50K | 70.55% |

## SMOTE

Before SMOTE, the training set contained:

- 29,687 lower-income observations
- 9,345 higher-income observations

After SMOTE:

- 29,687 lower-income observations
- 29,687 higher-income observations

SMOTE was applied only to the training data.

## Results After SMOTE

| Metric | KNN Result |
|---|---:|
| Accuracy | 81.98% |
| ROC-AUC | 0.9161 |
| Recall for > $50K | 84.89% |

The minority-class recall increased by approximately 18.96 percentage points.

## Key Findings

- KNN achieved the highest ROC-AUC before and after SMOTE.
- SMOTE substantially improved recall for the higher-income class.
- Improved recall came at the cost of lower overall accuracy.
- Accuracy alone was not sufficient for evaluating this imbalanced classification problem.
- The preferred model depends on whether overall accuracy or minority-class detection is more important.

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Imbalanced-learn
- SMOTE
- RobustScaler
- OneHotEncoder
- Matplotlib
- Jupyter Notebook

## Notebook

The complete Python analysis is available in:

`Flor_Trejo_Adult_Income_Classification_Case_Study.ipynb`

## Portfolio

This project is part of my Data Science portfolio:

https://flortr3.github.io/
