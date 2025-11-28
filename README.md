# 🚗 Vehicle Insurance Prediction — End-to-End MLOps Project

[![Python](https://img.shields.io/badge/Python-3.10-blue.svg)](https://www.python.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-green.svg)](https://www.mongodb.com/)
[![AWS](https://img.shields.io/badge/AWS-S3%20%7C%20EC2%20%7C%20ECR-orange.svg)](https://aws.amazon.com/)
[![Docker](https://img.shields.io/badge/Docker-Containerized-blue.svg)](https://www.docker.com/)
[![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-success.svg)](https://github.com/features/actions)

A production-ready machine learning project designed to automate the end-to-end lifecycle of a Vehicle Insurance Prediction model — including data ingestion, preprocessing, training, deployment, and monitoring using real MLOps tools and AWS cloud services.

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Project Structure](#-project-structure)
- [Setup & Installation](#-setup--installation)
- [Usage](#-usage)
- [Model Training](#-model-training)
- [Deployment & CI/CD](#-deployment--cicd)
- [AWS Services](#-aws-services)
- [Future Enhancements](#-future-enhancements)
- [Key Takeaways](#-key-takeaways)
- [Author](#-author)

---

## 🎯 Overview

Insurance companies need reliable insights to target customers who are more likely to purchase vehicle insurance. This project predicts **customer response (Yes/No)** based on past policy history and user demographics.

It follows the **complete MLOps lifecycle**:

**📌 Data → Pipeline → Model Training → Evaluation → Registry → Deployment → Live Inference**

---

## ✨ Features

| Capability | Description |
|------------|-------------|
| **Data Pipeline** | Auto ingestion from MongoDB Atlas |
| **Validation** | Schema-based checks before transformation |
| **Feature Engineering** | Robust preprocessing pipeline |
| **Model Selection** | Chooses best-performing model |
| **Model Registry** | Stored in AWS S3 for versioning |
| **UI for Prediction** | FastAPI with Jinja2 templates |
| **Deployment** | Docker on AWS EC2 |
| **CI/CD** | Fully automated GitHub Actions pipeline |

---

## ⚙️ Tech Stack

| Layer | Tools Used |
|-------|------------|
| **Programming** | Python 3.10 |
| **ML Frameworks** | Scikit-learn, Pandas, NumPy |
| **Database** | MongoDB Atlas |
| **Cloud** | AWS S3, ECR, EC2, IAM |
| **Web App** | FastAPI, HTML/CSS |
| **DevOps** | Docker, GitHub Actions, Self-hosted Runner |

---

## 🏗️ Architecture

```
MongoDB Atlas
    ↓
Data Ingestion → Data Validation → Data Transformation
    ↓
Model Training → Evaluation → Model Registry (S3)
    ↓
FastAPI App → Docker Image → ECR → CI/CD → AWS EC2 Deployment
```

---

## 📁 Project Structure

```
vehicle_ML_pipeline/
│
├── .github/workflows/          # CI/CD workflows
├── notebook/                   # Exploratory notebooks
├── src/
│   ├── components/            # Core ML components
│   ├── configuration/         # Config management
│   ├── constants/             # Constants and paths
│   ├── data_access/           # Data layer
│   ├── entity/                # Data entities
│   ├── pipline/               # Training & prediction pipelines
│   └── utils/                 # Utility functions
│
├── static/                    # Static assets
├── templates/                 # HTML templates
├── config/
│   └── schema.yaml           # Data validation schema
├── app.py                    # FastAPI application
├── requirements.txt          # Python dependencies
├── Dockerfile               # Container configuration
└── README.md               # Project documentation
```

---

## 🔧 Setup & Installation

### 1. Clone the Repository

```bash
git clone https://github.com/VEDA-2402/vehicle_ML_pipeline.git
cd vehicle_ML_pipeline
```

### 2. Create Virtual Environment

```bash
conda create -n vehicle python=3.10 -y
conda activate vehicle
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Set Environment Variables

```bash
export MONGODB_URL="your_mongodb_connection_string"
```

### 5. Run the Application

```bash
uvicorn app:app --host 0.0.0.0 --port 5000
```

**Visit:** `http://localhost:5000`

---

## 🚀 Usage

### Local Inference UI

1. Enter customer details using the web interface
2. Click **Predict**
3. Model returns **Response: Yes** or **Response: No**

---

## 🔥 Model Training

To manually trigger the full ML pipeline (training, evaluation & model push):

```
http://localhost:5000/train
```

**The pipeline will:**

- Fetch fresh data from MongoDB Atlas
- Validate data using schema rules
- Apply feature transformation pipeline
- Train & evaluate the model
- Push improved model to AWS S3 Model Registry

The latest best-performing model is automatically used for predictions. 🚀

---

## 🚀 Deployment & CI/CD

This project features **fully automated** CI/CD:

1. Developer pushes code to GitHub
2. GitHub Actions builds Docker image
3. Image pushed to AWS ECR
4. EC2 Self-Hosted Runner pulls & deploys container
5. App updates instantly with zero downtime ⚡

**Live Application URL:**

```
http://<your-ec2-public-ip>:5000
```

> ✔️ Works on laptop and Android/mobile browsers

---

## ☁️ AWS Services Used

| AWS Service | Purpose |
|-------------|---------|
| **EC2** | Deployment server + Self-Hosted Runner |
| **ECR** | Docker image registry |
| **S3** | Model registry (latest model stored here) |
| **IAM** | Secure access + credentials |
| **MongoDB Atlas** | Cloud database |

### Required GitHub Actions Secrets:

- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_DEFAULT_REGION`
- `ECR_REPO`
- `MONGODB_URL`

---

## 🔮 Future Enhancements

- Implement HTTPS using AWS Certificate Manager & Route 53
- Deploy scalable architecture using AWS ECS + Load Balancer
- Model monitoring with CloudWatch & Drift detection
- Modern UI upgrade (Tailwind/React)
- Experiment tracking using MLflow or DVC

---

## 🏆 Key Takeaways

✔️ Hands-on real-world MLOps Deployment  
✔️ Modular & scalable ML architecture  
✔️ Production CI/CD using AWS + Docker  
✔️ Cloud-based model versioning & registry  
✔️ DevOps + ML Engineering skills demonstrated

---

## ✨ Author

**Veda Vedhya**  
Machine Learning & Cloud Enthusiast | Finance & Data Aspirant

🔗 **GitHub:** [VEDA-2402](https://github.com/VEDA-2402)  
💼 **LinkedIn:** [veda-t-8b9a7134a](https://www.linkedin.com/in/veda-t-8b9a7134a/)

---

**If this project helped you, please ⭐ the repository!**

---

