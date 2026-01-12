# EXTENDED VERSION OF MLFLOW FOR MODEL MANAGEMENT AND EXPERIMENT TRACKING

This project implements a lightweight web-based dashboard integrated with **MLflow** to support machine learning experiment tracking, run comparison, and model explainability.

The system was developed for **academic purposes** to demonstrate practical usage of MLflow for experiment analysis and to enhance model transparency through SHAP-based explanations.

---

## Project Overview

The dashboard connects to an MLflow tracking server and allows users to:
- View logged experiment runs
- Compare model performance across runs
- Identify the best-performing run based on evaluation metrics
- Interpret model predictions using SHAP-inspired explainability

The scope of the project focuses on **analysis and evaluation**, not full production deployment.

---

## Implemented Features

### 1. Experiment Run Comparison
- Retrieves experiment runs logged in MLflow
- Displays metrics for each run
- Enables comparison between runs
- Identifies the best-performing run based on selected metrics

### 2. Model Explainability (SHAP)
- Provides SHAP-inspired feature contribution analysis
- Supports visualization of feature importance
- Helps explain how input features influence model predictions
- Integrated directly into the web dashboard

> **Note:** Only *run comparison* and *SHAP explainability* were implemented as additional web-based features.

---

## Technology Stack

### Backend / Machine Learning
- Python
- MLflow (experiment tracking)

### Frontend
- HTML
- CSS
- JavaScript

### Explainability
- SHAP-inspired feature contribution analysis

### Utilities
- Python HTTP server
- CORS proxy for API communication

---

## Project Structure

├── cors_proxy.py
├── frontend/
│ ├── index.html
│ ├── css/
│ └── js/
├── mlruns/ # MLflow experiment data
├── shap/ # SHAP-related logic and visualizations
└── README.md


---

## How to Run the Project

### Prerequisites
- Python 3.x
- Virtual environment (recommended)
- MLflow installed

---

### Execution Steps

Activate your virtual environment before running the commands below.

#### 1. Start the CORS Proxy
```bash
python cors_proxy.py
```

#### 2. Start the Frontend Server
```bash
python3 -m http.server 8000
```

#### 3. Start the CORS Proxy
```bash
mlflow server --host 0.0.0.0 --port 5000
```

## Access the Dashboard
Open a web browser and navigate to:
```bash
http://[::]:8000/
```

## System Workflow
1. Machine learning models are trained and logged using MLflow
2. Experiment runs and evaluation metrics are stored in the MLflow tracking server
3. The web dashboard retrieves run data via MLflow APIs
4. Users can:
 - Compare multiple experiment runs
 - Identify the best-performing model
 - View SHAP-based explainability visualizations

## Limitations
 - MLflow Model Registry is not implemented
 - Load testing was not conducted
 - SHAP values are calculated using an approximation approach rather than exact game-theoretic Shapley values
 - The system is intended for academic evaluation and demonstration purposes only

## Future Improvements
 - Integration with MLflow Model Registry
 - Automated fairness evaluation
 - Load and performance testing
 - Containerized deployment (Docker)
 - Enhanced explainability visualizations
