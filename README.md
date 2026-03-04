## IE7374 – MLOps Lab 2: FastAPI ML Inference Service

The objective of this lab is to build a production-style machine learning inference service using **FastAPI**. The project covers the complete workflow from model training and serialization to API deployment, automated testing, and CI validation.

This lab demonstrates important MLOps principles such as modular design, reproducibility, API-based model serving, test-driven validation, and continuous integration using GitHub Actions.

---

## Project Overview

This project implements a machine learning classification service that exposes a trained model through REST API endpoints.

The workflow includes:

- training a machine learning model on the Iris dataset
- serializing the trained model for reuse
- building a FastAPI application for prediction serving
- validating request payloads using Pydantic schemas
- testing API behavior using Pytest
- automating validation through GitHub Actions

---

## Problem Statement

The goal of this lab is to deploy a machine learning classifier as a web service that:

1. accepts structured input data
2. returns prediction results
3. provides confidence scores
4. includes a health monitoring endpoint
5. is automatically validated through a CI pipeline

---

## Model Details

- **Dataset:** Iris Dataset
- **Model Type:** Scikit-learn Classifier
- **Prediction Output:** Species class prediction (`0`, `1`, `2`)
- **Confidence Score:** Maximum predicted probability
- **Serialization Format:** Pickle (`.pkl`)

---

## Project Structure

```bash
IE7374_MLOps_LAB2_FastAPI/
│── src/
│   ├── train.py          # Model training script
│   ├── predict.py        # Prediction logic
│   ├── data.py           # Pydantic schemas
│   └── main.py           # FastAPI application
│
│── model/
│   └── iris_model.pkl    # Serialized trained model
│
│── test/
│   └── test_api_logic.py # Unit tests
│
│── .github/
│   └── workflows/
│       └── pytest_action.yml   # CI pipeline
│
│── requirements.txt
│── .gitignore
│── README.md
```

---

## Functionality

This project includes the following core components:

- **Model Training (`train.py`)**  
  Trains the machine learning classifier using the Iris dataset and saves the trained model as a serialized `.pkl` file.

- **Prediction Logic (`predict.py`)**  
  Loads the trained model and performs prediction on incoming input data.

- **Schema Validation (`data.py`)**  
  Defines structured request schemas using **Pydantic** to ensure valid API inputs.

- **FastAPI Application (`main.py`)**  
  Hosts the API endpoints for prediction and health checks.

- **Unit Testing (`test_api_logic.py`)**  
  Validates API functionality and response behavior.

---

## API Endpoints

The FastAPI service includes the following endpoints:

### 1. Prediction Endpoint
Accepts structured feature inputs and returns:
- predicted class label
- confidence score

### 2. Health Check Endpoint
Returns service status to confirm the API is running correctly.

---

## Tools and Technologies Used

- **Python**
- **FastAPI**
- **Uvicorn**
- **Scikit-learn**
- **Pydantic**
- **Pytest**
- **Git**
- **GitHub**
- **GitHub Actions**
- **Pickle**

---

## Testing

This project uses **Pytest** to validate the API logic and ensure reliable inference behavior.

The test suite covers:
- successful API responses
- prediction endpoint behavior
- validation of expected outputs
- correctness of health endpoint behavior

---

## Continuous Integration

This project includes a **GitHub Actions** workflow that runs automatically on every push.

### Configured Workflow

- **Pytest CI Pipeline**

The CI workflow helps ensure that:
- the API logic is automatically tested
- code changes do not break the service
- the project remains reproducible and validated in a clean environment

---

## Project Architecture

You can add the architecture image here in your GitHub README.

Example:

```markdown
![Project Architecture](path_to_your_image)
```

Or if the image is already uploaded to GitHub, you can use:

```markdown
![Project Architecture](your_image_link_here)
```

---

## Custom Enhancements Implemented

This lab includes several enhancements beyond the basic implementation:

- confidence score returned with predictions
- dedicated health monitoring endpoint
- clean modular separation across training, prediction, schema, and API layers
- structured repository architecture
- automated testing using **Pytest**
- CI validation using **GitHub Actions**

---

## Key Learnings

Through this lab, I learned:

- how to deploy a machine learning model as a REST API using **FastAPI**
- how to structure ML inference services in a modular way
- how to validate API inputs using **Pydantic**
- how to test API logic using **Pytest**
- how CI pipelines support reliable deployment workflows
- how MLOps combines software engineering and machine learning system design

---

## How to Run the Project Locally

Follow these steps to run the FastAPI service on your machine.

### 1. Clone the Repository

```bash
git clone <your-repository-link>
cd IE7374_MLOps_LAB2_FastAPI
```

### 2. Create and Activate a Virtual Environment

#### On Windows

```bash
python -m venv lab_02_env
lab_02_env\Scripts\activate
```

#### On macOS / Linux

```bash
python3 -m venv lab_02_env
source lab_02_env/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Train the Model

Run the training script if the serialized model file is not already present:

```bash
python src/train.py
```

### 5. Start the FastAPI Server

```bash
uvicorn src.main:app --reload
```

### 6. Open API Documentation

Once the server is running, open:

```text
http://127.0.0.1:8000/docs
```

This opens the interactive Swagger UI for testing the API endpoints.

---

## How to Run the Tests

Run the test suite using:

```bash
pytest
```

---

## Expected Outcome

After setup, the project should:

- train and save the machine learning model successfully
- start the FastAPI inference server locally
- expose prediction and health endpoints
- provide interactive API documentation via Swagger UI
- pass the Pytest test suite
- trigger GitHub Actions validation automatically on push

---

## Why This Project Matters

This lab goes beyond building a machine learning model by showing how a trained model can be operationalized as a reusable service.

It reflects real-world MLOps concepts such as:

- model packaging and serialization
- API-based model serving
- schema-driven input validation
- automated testing
- CI-based reliability checks
- modular architecture for maintainability

These are important foundations for deploying production-grade machine learning systems.

---

## Author

**Fatima Zehrah**  
Master’s in Data Analytics Engineering  
Northeastern University
