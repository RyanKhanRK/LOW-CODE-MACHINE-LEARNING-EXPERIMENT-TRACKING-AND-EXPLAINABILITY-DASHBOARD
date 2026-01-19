# LOW-CODE MACHINE LEARNING EXPERIMENT TRACKING & EXPLAINABILITY DASHBOARD

This project implements a lightweight web-based dashboard integrated with **MLflow** to support machine learning experiment tracking, run comparison, and model explainability.

The system was developed for **academic purposes** to demonstrate practical usage of MLflow for experiment analysis and to enhance model transparency through **SHAP-based explainability**.

---

## Project Overview

This project presents a low-code machine learning experiment tracking and explainability dashboard built on top of MLflow.

It extends MLflow’s default capabilities by introducing:

- Automated experiment and run handling through MLflow APIs
- Dataset-aware run comparison (same dataset only)
- Structured visualization of experiment metrics
- Integrated SHAP-based explainability
- A custom web-based dashboard for experiment analysis

The system is designed for academic and research use, focusing on reproducibility, transparency, and reduced manual interaction with MLflow’s default UI.

---

## Implemented Features

### Experiment Run Comparison

- Retrieves experiment runs logged in MLflow
- Displays evaluation metrics for each run
- Enables side-by-side comparison between runs
- Identifies the best-performing run based on selected metrics
- Restricts comparison to runs from the same dataset

### Model Explainability (SHAP)

- Provides SHAP-based feature contribution analysis
- Visualizes feature importance and influence on predictions
- Supports both global and local interpretability
- Integrated directly into the web dashboard

> **Note:**  
> Only run comparison and SHAP explainability were implemented as additional web-based features.

---

## Technology Stack

### Backend / Machine Learning

- Python
- MLflow

### Frontend

- HTML
- CSS
- JavaScript

### Explainability

- SHAP-based feature contribution analysis

### Utilities

- Python HTTP server
- CORS proxy for API communication

---

## Project Structure

├── cors_proxy.py
├── frontend/
│   ├── index.html
│   ├── css/
│   └── js/
├── mlruns/          # MLflow experiment data
├── shap/            # SHAP-related logic and visualizations
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

#### 4. Start the Backend Server
```bash
python3 model_server.py
```

## Access the Dashboard
Open a web browser and navigate to:
```bash
http://localhost:8000/
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
