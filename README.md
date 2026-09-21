# loan-approval-prediction
#  Loan Approval Prediction System  An interactive **Machine Learning-based Loan Approval Prediction System** built with **React, TypeScript, and Vite**. The application analyzes historical loan application data, trains classification models, evaluates their performance, and predicts whether a new loan application is likely to be **Approved or 
#  Loan Approval Prediction System

An interactive **Machine Learning-based Loan Approval Prediction System** built with **React, TypeScript, and Vite**. The application analyzes historical loan application data, trains classification models, evaluates their performance, and predicts whether a new loan application is likely to be **Approved or Rejected**.

The project combines a modern web dashboard with an end-to-end machine learning workflow including **data preprocessing, feature engineering, encoding, model training, prediction, and performance analysis**.

---

##  Features

*  Interactive loan analytics dashboard
*  Loan approval prediction using Machine Learning
*  Logistic Regression model
*  Decision Tree classifier
*  Data cleaning and preprocessing
*  Automated feature engineering
*  Numerical feature standardization
*  Categorical feature encoding
*  Loan application analysis
*  Approval probability prediction
*  Model performance comparison
*  Confusion matrix visualization
  * Feature importance analysis
*  Probability distribution analysis
*  Prediction threshold analysis
*  Loan prediction report generation
*  Responsive React-based interface

---

## Machine Learning Workflow

The application follows an end-to-end ML pipeline:

```text
Raw Loan Dataset
       ↓
Data Cleaning & Validation
       ↓
Missing Value Imputation
       ↓
Duplicate Removal
       ↓
Feature Engineering
       ↓
Categorical Encoding
       ↓
Numerical Standardization
       ↓
80/20 Stratified Train-Test Split
       ↓
Model Training
   ┌───────────────┐
   │               │
   ▼               ▼
Logistic       Decision
Regression       Tree
   │               │
   └───────┬───────┘
           ▼
     Model Evaluation
           ↓
     Loan Prediction
```

---

##  Machine Learning Models

### 1. Logistic Regression

Logistic Regression is used as a classification model to estimate the probability of loan approval.

The implementation uses:

* Gradient-based training
* Learning rate: `0.12`
* 450 training epochs
* L2 regularization
* Standardized numerical features

### 2. Decision Tree

A Decision Tree classifier is also trained on the loan application dataset.

The model is configured with:

* Maximum depth: `5`
* Minimum samples per split: `8`

The application evaluates both models on the test dataset and selects the model using a composite score based on:

* F1 Score: 60%
* Accuracy: 40%

---

##  Model Evaluation

The application calculates several classification metrics:

* Accuracy
* Precision
* Recall
* F1 Score
* ROC-AUC
* Confusion Matrix

The dashboard also provides visual representations of model performance and feature importance.

---

##  Data Preprocessing

The preprocessing pipeline handles:

### Numerical Data

The system validates and imputes:

* Applicant income
* Coapplicant income
* Loan amount
* Loan term
* Applicant age
* Monthly debt
* Credit history
* Dependents
* Existing loans

Median-based imputation is used for several numerical fields.

### Categorical Data

Categorical values are normalized for:

* Education
* Marital status
* Employment status
* Self-employment
* Property area
* Property type
* Loan purpose

Invalid or missing loan-status records are excluded from supervised model training.

Duplicate records are also removed.

---

##  Feature Engineering

Additional features are generated from the original dataset.

### Total Income

```text
Total Income = Applicant Income + Coapplicant Income
```

### Debt-to-Income Ratio

```text
DTI = Monthly Debt / Monthly Income
```

### Loan-to-Income Ratio

```text
LTI = Loan Amount / Total Income
```

Additional derived features include:

* Age Group
* Income Group
* Loan Amount Group
* Existing Loans Indicator
* Credit History Indicator

---

##  Dataset

The project includes:

```text
public/data/loan_applications.csv
```

The dataset contains **520 loan application records** with attributes such as:

| Feature              | Description                |
| -------------------- | -------------------------- |
| `loan_id`            | Unique loan application ID |
| `applicant_income`   | Applicant income           |
| `coapplicant_income` | Coapplicant income         |
| `loan_amount`        | Requested loan amount      |
| `loan_term`          | Loan repayment term        |
| `credit_history`     | Credit history indicator   |
| `employment_status`  | Employment category        |
| `education`          | Education level            |
| `marital_status`     | Marital status             |
| `dependents`         | Number of dependents       |
| `self_employed`      | Self-employment status     |
| `property_area`      | Property location type     |
| `property_type`      | Property type              |
| `existing_loans`     | Number of existing loans   |
| `monthly_debt`       | Monthly debt obligation    |
| `applicant_age`      | Applicant age              |
| `loan_purpose`       | Purpose of the loan        |
| `loan_status`        | Target: Approved/Rejected  |

---

##  Application Pages

### Dashboard

Provides an overview of:

* Total loan applications
* Approved and rejected applications
* Approval rate
* Income statistics
* Loan statistics
* Credit history statistics
* Historical insights

### Loan Predictor

Allows users to enter applicant information and receive:

* Predicted loan status
* Approval probability
* Rejection probability
* Confidence
* Model used
* Contributing factors

### Loan Analysis

Provides analysis of loan approvals based on:

* Income
* Loan amount
* Credit history
* Education
* Employment
* Property area
* Loan purpose
* Age groups

### Model Performance

Displays:

* Accuracy
* Precision
* Recall
* F1 Score
* ROC-AUC
* Confusion matrix
* Feature importance
* Probability distributions
* Threshold analysis

---

##  Technology Stack

### Frontend

* React
* TypeScript
* Vite
* Tailwind CSS
* Recharts
* Lucide React
* Motion

### Machine Learning

* Logistic Regression
* Decision Tree
* Feature Engineering
* Data Encoding
* Statistical Metrics

### Data Processing

* PapaParse
* CSV processing
* Data validation
* Missing value imputation
* Standardization

### Reporting

* jsPDF
* html2canvas

---

##  Project Structure

```text
loan-approval-prediction/
│
├── public/
│   └── data/
│       └── loan_applications.csv
│
├── src/
│   ├── components/
│   │   ├── Sidebar.tsx
│   │   ├── Header.tsx
│   │   ├── LoanPredictionForm.tsx
│   │   ├── PredictionResult.tsx
│   │   ├── LoanTable.tsx
│   │   ├── ModelMetrics.tsx
│   │   ├── ConfusionMatrix.tsx
│   │   ├── FeatureImportanceChart.tsx
│   │   └── ...
│   │
│   ├── ml/
│   │   ├── preprocessing.ts
│   │   ├── featureEngineering.ts
│   │   ├── encoding.ts
│   │   ├── logisticRegression.ts
│   │   ├── decisionTree.ts
│   │   └── modelTraining.ts
│   │
│   ├── pages/
│   │   ├── Dashboard.tsx
│   │   ├── LoanPredictor.tsx
│   │   ├── LoanAnalysis.tsx
│   │   └── ModelPerformance.tsx
│   │
│   ├── services/
│   │   └── dataset.ts
│   │
│   ├── utils/
│   │   ├── metrics.ts
│   │   ├── loanAnalysis.ts
│   │   ├── insights.ts
│   │   └── reportGenerator.ts
│   │
│   ├── types.ts
│   ├── App.tsx
│   ├── main.tsx
│   └── index.css
│
├── .env.example
├── package.json
├── tsconfig.json
├── vite.config.ts
└── README.md
```

---

##  Installation

### Prerequisites

Make sure you have installed:

* Node.js
* npm

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/loan-approval-prediction.git
cd loan-approval-prediction
```

### 2. Install dependencies

```bash
npm install
```

### 3. Start the development server

```bash
npm run dev
```

The application will be available through the local Vite development server.

---

##  Build for Production

To create a production build:

```bash
npm run build
```

To preview the production build:

```bash
npm run preview
```

---

##  Type Checking

The project also provides a TypeScript lint/type-check command:

```bash
npm run lint
```

---

##  Prediction Process

Users provide information such as:

* Age
* Education
* Employment
* Income
* Coapplicant income
* Existing loans
* Monthly debt
* Loan amount
* Loan term
* Credit history
* Property details
* Loan purpose

The application processes the information and generates:

```text
Applicant Information
        ↓
Feature Engineering
        ↓
Feature Encoding
        ↓
Trained ML Model
        ↓
Approval Probability
        ↓
Approved / Rejected
```

---

##  Important Note

This project is intended for **educational and demonstration purposes**. Model predictions are based on patterns learned from the included historical dataset and should not be treated as actual financial or lending decisions.

---

##  Future Improvements

Possible improvements include:

* Integration with larger real-world datasets
* Additional ML algorithms such as Random Forest, XGBoost and SVM
* Hyperparameter optimization
* Cross-validation
* Advanced explainable AI techniques
* Fairness and bias analysis
* Model versioning
* Backend API integration
* Database integration
* User authentication
* Cloud deployment
* Real-time model monitoring
* Automated model retraining

---

##  Project

**Loan Approval Prediction System**

Built as a Machine Learning and Web Development project demonstrating how ML models can be integrated into an interactive web application.
