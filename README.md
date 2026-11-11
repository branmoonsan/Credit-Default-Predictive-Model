# Credit Default Prediction Using Machine Learning

## Project Overview

This project applies machine learning classification techniques to predict creditworthiness using the German Credit Dataset.

Credit risk assessment is an important process for financial institutions when evaluating borrowers. By analyzing historical credit data and borrower characteristics, machine learning models can help identify potential credit risks and support more informed lending decisions.

The project explores different classification algorithms, evaluates their predictive performance, and compares their effectiveness in credit risk prediction.

## Objectives

- Explore and understand credit-related data through Exploratory Data Analysis (EDA).
- Identify relationships between borrower characteristics and creditability.
- Prepare data for machine learning model development.
- Build classification models to predict creditability.
- Evaluate and compare model performance using classification metrics.
- Apply hyperparameter tuning to optimize model configurations.

## Dataset

**German Credit Dataset**

The dataset contains borrower and credit-related attributes, including:

- Existing account status
- Credit history
- Loan purpose
- Credit amount
- Savings and bonds
- Employment duration
- Percentage of disposable income
- Age
- Housing
- Occupation
- Number of existing credits
- Creditability (target variable)

The target variable is `creditability`.

*Note: The original dataset file is named `german_credit_data.csv`. It is not included in this repository and must be obtained separately to run the notebook.*

## Project Workflow

### 1. Data Loading and Preparation
- Load the dataset using Pandas.
- Rename variables for better readability.
- Inspect dataset dimensions, data types and descriptive statistics.
- Examine unique values and variable distributions.

### 2. Exploratory Data Analysis (EDA)
- Analyze numerical variable distributions.
- Examine creditability distribution.
- Explore relationships between creditability and borrower characteristics.
- Investigate correlations between numerical variables.
- Visualize patterns using Matplotlib and Seaborn.

### 3. Feature Selection and Data Splitting
- Separate independent variables (predictors) from the target variable.
- Split the dataset into training and testing sets.
- Use a 70:30 train-test split.

### 4. Model Development

Three classification algorithms are implemented:

**Logistic Regression**
- Develop a baseline classification model.
- Evaluate predictions using classification metrics.
- Analyze the ROC curve and AUC.
- Perform 3-fold cross-validation.

**Decision Tree Classifier**
- Develop a tree-based classification model.
- Restrict maximum tree depth to 3.
- Visualize the decision tree structure.

**Random Forest Classifier**
- Develop an ensemble classification model.
- Configure 100 decision trees (`n_estimators=100`).
- Set maximum tree depth to 7.

### 5. Hyperparameter Tuning

Apply two hyperparameter optimization techniques to Logistic Regression:

- GridSearchCV
- RandomizedSearchCV

The parameter search explores different values of `dual` and `max_iter`, using 3-fold cross-validation and accuracy as the scoring metric.

## Model Evaluation and Results

The models are evaluated using accuracy, precision, recall, confusion matrix and other classification metrics where implemented.

### Model Accuracy Comparison

| Classification Model | Accuracy |
|---|---:|
| Logistic Regression | 76.67% |
| Decision Tree | 73.33% |
| Random Forest | 76.33% |

### Logistic Regression Evaluation

| Evaluation Metric | Result |
|---|---:|
| Accuracy | 76.67% |
| Precision | 79.32% |
| Recall | 89.95% |

The Logistic Regression model achieved an accuracy of approximately 76.67%, with a recall of approximately 89.95%.

### Hyperparameter Tuning Results

Both GridSearchCV and RandomizedSearchCV returned the following best configuration:

- `dual`: False
- `max_iter`: 100
- Best cross-validation accuracy: 72.9981%

## Technologies and Libraries

- **Python** – Programming language
- **Jupyter Notebook** – Development environment
- **Pandas** – Data manipulation and analysis
- **NumPy** – Numerical computing
- **Matplotlib** – Data visualization
- **Seaborn** – Statistical data visualization
- **Scikit-learn** – Machine learning, classification and model evaluation
- **pydotplus** – Decision tree visualization

## Repository Structure

```text
credit-default-prediction/
│
├── predictive_model_credit_defaulters.ipynb
├── README.md
├── requirements.txt
│
└── data/
    └── german_credit_data.csv (optional)
```

## How to Run the Project

1. Clone this repository:

```bash
git clone https://github.com/YOUR-USERNAME/credit-default-prediction.git
```

2. Navigate to the project directory:

```bash
cd credit-default-prediction
```

3. Install the required libraries:

```bash
pip install -r requirements.txt
```

4. Place `german_credit_data.csv` in the project root directory (or update the dataset path in the notebook).

5. Open Jupyter Notebook:

```bash
jupyter notebook
```

6. Open `predictive_model_credit_defaulters.ipynb` and run the cells.

## Key Takeaways

This project demonstrates the application of supervised machine learning classification techniques to credit risk prediction.

Through exploratory data analysis, model development, cross-validation and hyperparameter tuning, the project explores how different classification algorithms can be applied to borrower creditability assessment.

The results show that Logistic Regression and Random Forest achieved relatively similar accuracy, while Decision Tree achieved a slightly lower accuracy on the test dataset.

Further improvements could include feature scaling, class imbalance analysis, systematic feature selection, and additional model optimization.

---

**Disclaimer:** This project is developed for educational and portfolio purposes. The models are not intended for actual lending decisions or financial risk assessments.
