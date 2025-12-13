# Diabetes Health Indicators Analysis

This repository contains the preprocessing, analysis, and evaluation workflow for the Diabetes Health Indicators Dataset available on Kaggle. The focus of this project is on exploring the dataset, handling feature types, addressing class imbalance, and evaluating different preprocessing and pipeline strategies.

## Dataset
The dataset can be accessed at [Kaggle: Diabetes Health Indicators Dataset](https://www.kaggle.com/datasets/mohankrishnathalla/diabetes-health-indicators-dataset/data). It contains information about various health indicators such as glucose level, blood pressure, body mass index, and more, along with each individual's diabetes status.

## Data Cleaning
Numerical features were standardized to account for skewed distributions, while categorical features were encoded using ordinal or one-hot encoding depending on their type.

## Handling Class Imbalance
The dataset is slightly imbalanced toward the negative class (no diabetes). To address this, SMOTE (Synthetic Minority Over-sampling Technique) has been applied to the training set to balance the classes. Both baseline and SMOTE pipelines are evaluated to assess the impact of resampling.

## Feature Processing
Features are grouped into numerical, ordinal, and nominal types. Pipelines are used to transform these features for analysis. Numerical features are standardized using `StandardScaler`, ordinal features are encoded with `OrdinalEncoder`, and nominal features are encoded using `OneHotEncoder`.

## Evaluation Workflow
A systematic evaluation pipeline has been implemented to train and test multiple classifiers, compute performance metrics (accuracy, precision, recall, F1 score), plot ROC and precision-recall curves, and save confusion matrices. Hyperparameter tuning is also incorporated for each model using GridSearchCV with 5-fold cross-validation.

## Directory Structure
- `data/` : Contains the resulting metrics table as CSV files.  
- `Baseline/ - SMOTE/ - Hyper/` : Contains generated ROC/PR curves and confusion matrices.  
- `diabeto2.0` : Jupiter Notebook for preprocessing, pipelines, and evaluation.
- `diabeto3.0` : Jupiter Notebook for preprocessing, pipelines, and evaluation with parallel training to reduce final tuning time for hyperparameters optimization (install joblib library to run the parallelization).  

## Usage
To reproduce the analysis:
1. Clone the repository.
2. Install the dependencies listed in `requirements.txt`.
3. Run the scripts in `Diabeto2.0`/`Diabeto3.0` for preprocessing, pipeline building, and evaluation.
 Generated plots and results will be saved in the `Baseline/Smote/Hyper` and `data/` folders.

