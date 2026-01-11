# EXTENDED VERSION OF MLFLOW FOR MODEL MANAGEMENT AND EXPERIMENT TRACKING

This project is a web-based dashboard built on top of MLflow to support experiment tracking, model comparison, and explainability. The system allows users to monitor logged experiments, identify the best-performing runs, and interpret model predictions using SHAP-based visualizations.

The focus of this project is experiment analysis and explainability, rather than full deployment or model registry management.

🚀 Features
✅ Experiment Run Comparison
Displays all logged MLflow runs for an experiment

Compares runs based on evaluation metrics

Highlights the best-performing run

Helps users analyze model performance differences

✅ Model Explainability (SHAP)
Visualizes SHAP-inspired feature importance

Supports global and local explainability

Helps understand how features influence predictions

Integrated directly into the dashboard UI

⚠️ Note: Only run comparison and SHAP explainability were implemented as extended features in the web interface.

🛠️ Tech Stack
Backend / ML

Python

MLflow (experiment tracking)

Frontend

HTML, CSS, JavaScript

Explainability

SHAP-inspired feature contribution analysis

Server / Utilities

Python HTTP server

CORS proxy for API communication

📂 Project Structure (Simplified)
├── cors_proxy.py
├── frontend/
│   ├── index.html
│   ├── css/
│   └── js/
├── mlruns/              # MLflow experiment data
├── shap/                # SHAP-related logic and visualizations
└── README.md
▶️ How to Run the Project
Prerequisites
Python 3.x

Virtual environment recommended

MLflow installed

Step-by-Step Execution
Activate your virtual environment first.

1️⃣ Start the CORS Proxy
python cors_proxy.py
2️⃣ Start the Frontend Server
python3 -m http.server 8000
3️⃣ Start the MLflow Tracking Server
mlflow server --host 0.0.0.0 --port 5000
🌐 Access the Application
Open your browser and go to:

[http://[::]:8000/](http://[::]:8000/
)
📈 How It Works (High-Level)
Models are trained and logged using MLflow

Experiment runs and metrics are stored in the MLflow backend

The web dashboard fetches run data via MLflow APIs

Users can:

Compare runs and identify the best model

View SHAP-based explainability results

SHAP visualizations help interpret feature contributions

⚠️ Limitations
MLflow Model Registry is not implemented

Load testing was not performed

SHAP values are computed using an approximation approach, not full game-theoretic Shapley values

The system is designed for academic evaluation and analysis, not production deployment

🔮 Future Improvements
Integration with MLflow Model Registry

Automated fairness evaluation

Load testing and scalability analysis

Deployment using containerization (Docker)

Enhanced SHAP visualizations and interactivity

📌 Academic Note
This project was developed as part of a final-year academic submission. The focus is on experiment tracking, model comparison, and explainability, demonstrating practical machine learning system design and evaluation.


