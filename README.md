```bash
███████╗██████╗  █████╗ ██╗   ██╗██████╗     ██████╗ ███████╗████████╗███████╗ ██████╗████████╗
██╔════╝██╔══██╗██╔══██╗██║   ██║██╔══██╗    ██╔══██╗██╔════╝╚══██╔══╝██╔════╝██╔════╝╚══██╔══╝
█████╗  ██████╔╝███████║██║   ██║██║  ██║    ██║  ██║█████╗     ██║   █████╗  ██║        ██║   
██╔══╝  ██╔══██╗██╔══██║██║   ██║██║  ██║    ██║  ██║██╔══╝     ██║   ██╔══╝  ██║        ██║   
██║     ██║  ██║██║  ██║╚██████╔╝██████╔╝    ██████╔╝███████╗   ██║   ███████╗╚██████╗   ██║   
╚═╝     ╚═╝  ╚═╝╚═╝  ╚═╝ ╚═════╝ ╚═════╝     ╚═════╝ ╚══════╝   ╚═╝   ╚══════╝ ╚═════╝   ╚═╝   

Production-Grade Fraud Detection System
ML Model + FastAPI + Docker + Monitoring
```

---

# > SYSTEM OVERVIEW

```bash
This is NOT just a model.

This is a complete machine learning system that:

[✔] Trains a fraud detection model
[✔] Serves predictions via API
[✔] Runs inside Docker
[✔] Logs predictions
[✔] Detects data drift
[✔] Ready for cloud deployment
```

---

# > ARCHITECTURE

```bash
Client / Application
        ↓
    FastAPI Backend
        ↓
    Loaded ML Model
        ↓
Fraud Probability + Label
        ↓
Logging + Drift Monitoring
```

---

# > PROBLEM STATEMENT

```bash
Goal:
Predict whether a transaction is fraudulent in real-time.

Input Features:
- amount
- hour
- merchant category
- location
- device type
- historical features

Output:
- fraud_probability (0–1)
- prediction (Fraud / Not Fraud)
```

---

# > MACHINE LEARNING PIPELINE

```bash
Fraud data is HIGHLY imbalanced.
Accuracy = meaningless.

We use:
- Stratified split
- Cross-validation
- Class weighting
- Imbalance handling techniques
```

### Models

```bash
- XGBoost
- LightGBM
- Logistic Regression (baseline)
```

### Evaluation Metrics (Critical)

```bash
- ROC-AUC
- Precision
- Recall
- F1-score
- PR-AUC
- Confusion Matrix
- False Negative Cost Analysis
```

---

# > MODEL SERIALIZATION

```bash
After training:

model.pkl saved using:
- joblib
- pickle
- or native XGBoost save

Training Environment ≠ Production Environment
```

---

# > API LAYER (FastAPI)

```bash
POST /predict
```

### Example Request

```json
{
  "amount": 2500,
  "merchant_type": "electronics",
  "device": "mobile",
  "hour": 22
}
```

### Example Response

```json
{
  "fraud_probability": 0.87,
  "prediction": "Fraud"
}
```

Run locally:

```bash
uvicorn api.main:app --reload
```

Swagger UI:

```bash
http://127.0.0.1:8000/docs
```

---

# > DOCKERIZATION

```bash
Why Docker?

- Portable
- Reproducible
- Deployable anywhere
- Industry standard
```

Build & Run:

```bash
docker build -t fraud-api .
docker run -p 8000:8000 fraud-api
```

---

# > MONITORING (Production Feature)

## 1. Prediction Logging

```bash
Logs stored:
- Input features
- Prediction
- Probability
- Timestamp
```

## 2. Data Drift Detection

```bash
Compare:
Training Distribution
        vs
Live Incoming Data

Methods:
- KS-Test
- Population Stability Index (PSI)

If drift detected → Alert
```

Example:

```bash
If avg transaction amount suddenly doubles → drift warning
```

---

# > OPTIONAL DASHBOARD

```bash
Can be built using:
- Streamlit
- Custom monitoring endpoint

Displays:
- Fraud rate
- Drift alerts
- Feature shifts
- Prediction counts
```

---

# > PROJECT STRUCTURE

```bash
fraud-detection/
│
├── data/
├── notebooks/
├── src/
│   ├── preprocess.py
│   ├── train.py
│   ├── evaluate.py
│
├── models/
│   └── model.pkl
│
├── api/
│   └── main.py
│
├── monitoring/
│   └── drift.py
│
├── Dockerfile
├── requirements.txt
└── README.md
```

---

# > INSTALLATION

```bash
git clone https://github.com/your-username/fraud-detection.git
cd fraud-detection

python -m venv venv
source venv/bin/activate

pip install -r requirements.txt
```

---

# > DEPLOYMENT OPTIONS

```bash
- AWS EC2
- AWS ECS
- GCP Cloud Run
- Azure App Service
- Render / Railway
```

---

# > WHY THIS PROJECT MATTERS

```bash
Demonstrates:

[✔] Strong ML fundamentals
[✔] Handling imbalanced data correctly
[✔] Clean architecture
[✔] Model serialization
[✔] REST API development
[✔] Docker knowledge
[✔] Monitoring awareness
[✔] Production thinking
```

Transforms you from:

```bash
ML Student
```

Into:

```bash
ML Engineer Candidate
```

---

# > LICENSE

```bash
MIT License
```

---

# > AUTHOR

```bash
Sachin Maurya
Machine Learning Engineer
```

---

