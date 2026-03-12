🚀 FastAPI Insurance Prediction API

This project is a Machine Learning powered REST API built using FastAPI that predicts insurance cost based on user attributes such as:

Age

Height

Weight

BMI

City

Smoking Status

The trained ML model is saved using Pickle (.pkl) and loaded inside the FastAPI application to make real-time predictions.

📌 Project Overview

The goal of this project is to demonstrate how to:

Train a Machine Learning model on an Insurance Dataset

Save the trained model using Pickle

Build a FastAPI backend

Load the ML model into the API

Create a prediction endpoint

Return predictions in JSON format

This architecture is commonly used in production ML systems where models are served through APIs.

🏗 Project Structure
insurance-fastapi-ml/
│
├── model.pkl                # Trained ML Model
├── main.py                  # FastAPI application
├── requirements.txt         # Project dependencies
├── insurance.csv            # Dataset (optional)
├── train_model.py           # Model training script
└── README.md                # Project documentation

🧠 Machine Learning Model

The ML model is trained using features such as:

Feature	Description
Age	Age of the person
Height	Height in cm
Weight	Weight in kg
BMI	Body Mass Index
City	Tier based city
Smoker	Smoking status

The trained model predicts the insurance cost or insurance risk depending on the training objective.

The model is saved using:

import pickle

pickle.dump(model, open("model.pkl", "wb"))

⚡ FastAPI Integration

FastAPI loads the trained model during application startup.

import pickle

with open("model.pkl", "rb") as f:
    model = pickle.load(f)


The API receives user data, converts it to a DataFrame, and returns the prediction.

📡 API Endpoint
POST /predict

Predict insurance value based on user input.

Request Body
{
  "age": 30,
  "height": 170,
  "weight": 70,
  "bmi": 24.2,
  "city": "Delhi",
  "smoker": "no"
}

Response
{
  "predicted_insurance": 15234.75
}

🛠 Installation

Clone the repository:

git clone https://github.com/yourusername/insurance-fastapi-ml.git


Move into the project directory:

cd insurance-fastapi-ml


Install dependencies:

pip install -r requirements.txt

▶️ Run the FastAPI Server

Start the server using Uvicorn:

uvicorn main:app --reload


Server will run at:

http://127.0.0.1:8000

📘 API Documentation

FastAPI automatically generates documentation.

Swagger UI:

http://127.0.0.1:8000/docs


Alternative docs:

http://127.0.0.1:8000/redoc

📦 Requirements

Example requirements.txt:

fastapi
uvicorn
pandas
scikit-learn
pydantic
numpy

💡 Example Workflow

1️⃣ Train ML model
2️⃣ Save model using Pickle
3️⃣ Build FastAPI backend
4️⃣ Load model inside API
5️⃣ Send request to /predict
6️⃣ Receive prediction response

🔮 Future Improvements

Add Docker support

Deploy on AWS / GCP / Render

Add input validation

Implement model versioning

Add CI/CD pipeline

👨‍💻 Author

Honey Verma

B.Tech AI Student | Machine Learning Enthusiast
