# loan-approval-prediction
#  Loan Approval Prediction using Machine Learning  A web-based **Loan Approval Prediction System** that uses Machine Learning to predict whether a loan application is likely to be **Approved or Rejected** based on applicant financial, demographic, employment, credit, and loan-related information.  
#  Loan Approval Prediction using Machine Learning

A web-based **Loan Approval Prediction System** that uses Machine Learning to predict whether a loan application is likely to be **Approved or Rejected** based on applicant financial, demographic, employment, credit, and loan-related information.

The application provides an interactive dashboard for exploring loan application data, making individual predictions, analyzing approval patterns, and evaluating machine-learning model performance.

##  Features

*  **Interactive Dashboard** – View loan application statistics, approval rates, income patterns, loan amounts, employment categories, and other insights.
*  **Loan Approval Prediction** – Enter applicant details and predict the probability of loan approval or rejection.
*  **Multiple ML Models** – Compares:

  * Logistic Regression
  * Decision Tree
*  **Model Performance Evaluation** – Displays:

  * Accuracy
  * Precision
  * Recall
  * F1 Score
  * ROC-AUC
  * Confusion Matrix
*  **Feature Importance Analysis** – Identifies the factors that have the greatest influence on predictions.
*  **Probability & Threshold Analysis** – Examines prediction probabilities and classification thresholds.
*  **Financial Analysis** – Analyzes applicant income, loan amount, monthly debt, debt-to-income ratio, and loan-to-income ratio.
*  **Loan Application Analysis** – Explore approval patterns based on credit history, education, employment, property area, loan purpose, age, and other factors.
*  **Model Retraining** – Allows models to be retrained using the available dataset.
*  **PDF Report Generation** – Generates an underwriting/loan analysis report.
*  **Browser-Based ML** – Data preprocessing and model training are implemented in TypeScript and run within the web application.

##  Technologies Used

* **React**
* **TypeScript**
* **Vite**
* **Tailwind CSS**
* **Recharts**
* **PapaParse**
* **Lucide React**
* **JavaScript/TypeScript Machine Learning**
* **Logistic Regression**
* **Decision Tree**
* **jsPDF**
* **HTML2Canvas**

##  Machine Learning Workflow

The project follows a complete machine-learning pipeline:

```text
Loan Application Dataset
        ↓
Data Cleaning & Preprocessing
        ↓
Missing Value Handling
        ↓
Feature Engineering
        ↓
Categorical Encoding
        ↓
Feature Standardization
        ↓
80/20 Stratified Train-Test Split
        ↓
Model Training
   ┌───────────────┐
   │ Logistic      │
   │ Regression    │
   └───────────────┘
          +
   ┌───────────────┐
   │ Decision Tree │
   └───────────────┘
        ↓
Model Evaluation
        ↓
Best Model Selection
        ↓
Loan Approval Prediction
```

##  Input Features

The prediction system considers several applicant and loan characteristics, including:

* Applicant age
* Marital status
* Number of dependents
* Education
* Employment status
* Self-employment status
* Applicant income
* Co-applicant income
* Existing loans
* Monthly debt
* Loan amount
* Loan term
* Loan purpose
* Property type
* Property area
* Credit history

### Engineered Features

The system also derives additional features such as:

* Total combined income
* Debt-to-income (DTI) ratio
* Loan-to-income (LTI) ratio
* Age group
* Income group
* Loan amount group
* Existing-loan indicator
* Credit-history indicator

##  Model Evaluation

The application uses an **80/20 stratified train-test split**. The encoder is fitted only on the training data to reduce the risk of data leakage.

Both Logistic Regression and Decision Tree models are evaluated using standard classification metrics, and the application identifies the better-performing model based on its evaluation results.

##  Project Structure

```text
src/
├── components/
│   ├── LoanPredictionForm.tsx
│   ├── PredictionResult.tsx
│   ├── ModelMetrics.tsx
│   ├── ConfusionMatrix.tsx
│   ├── FeatureImportanceChart.tsx
│   └── ...
│
├── ml/
│   ├── preprocessing.ts
│   ├── featureEngineering.ts
│   ├── encoding.ts
│   ├── logisticRegression.ts
│   ├── decisionTree.ts
│   └── modelTraining.ts
│
├── pages/
│   ├── Dashboard.tsx
│   ├── LoanPredictor.tsx
│   ├── LoanAnalysis.tsx
│   └── ModelPerformance.tsx
│
├── services/
│   └── dataset.ts
│
├── utils/
│   ├── metrics.ts
│   ├── loanAnalysis.ts
│   ├── insights.ts
│   └── reportGenerator.ts
│
├── App.tsx
└── types.ts
```

## How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
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

### 4. Open the application

Open the local Vite development URL shown in your terminal.

##  Project Objective

The main objective of this project is to demonstrate how **Machine Learning and Data Analytics can be applied to loan underwriting**. By analyzing historical loan applications and applicant characteristics, the system provides a data-driven prediction of loan approval outcomes while also giving users insights into model performance and the factors influencing predictions.

##  Future Enhancements

* Integration with a real-time banking/loan database
* Advanced models such as Random Forest, XGBoost, or Neural Networks
* Model explainability using SHAP or similar techniques
* User authentication and role-based access
* Cloud deployment
* Automated model monitoring
* Fairness and bias analysis
* Real-time API-based prediction service

##  Disclaimer

This project is intended for **educational and demonstration purposes**. Predictions should not be treated as actual financial or lending decisions.

##  Project Type

**BCA Final Year / Machine Learning Project**

**Domain:** Machine Learning + Data Analytics + Financial Technology
