# 🧠 Brain Tumor Detection using Federated Learning

This project implements a **privacy-preserving brain tumor detection system** using **Federated Learning (FL)**. It uses MRI images to detect the presence of a tumor and estimates its **severity percentage** along with a **medical description** — all without directly sharing patient data.

---

## 📌 Table of Contents

1. [📖 Project Overview](#-project-overview)  
2. [🛠 Tech Stack Used](#-tech-stack-used)  
3. [🔄 How Federated Learning Works](#-how-federated-learning-works)  
4. [🧬 Dataset Details](#-dataset-details)  
5. [🤖 Model Details](#-model-details)  
6. [📊 Severity Prediction Logic](#-severity-prediction-logic)  
7. [🖥️ Frontend & Backend](#-frontend--backend)  
8. [📈 Project Flowchart](#-project-flowchart)  
9. [🚀 How to Run the Project](#-how-to-run-the-project)  
10. [✅ Conclusion](#-conclusion)

---

## 📖 Project Overview

Brain tumor detection via MRI is crucial in early diagnosis and treatment. This project prioritizes **data privacy** by using **Federated Learning**, where patient data never leaves the device or hospital.

### 🔍 Features:
- Detects presence of brain tumor (Yes/No)
- Predicts severity percentage
- Shows severity level with a medical advisory
- Deploys results on a clean web interface

---

## 🛠 Tech Stack Used

| Component        | Tech Used             |
|------------------|------------------------|
| Model            | TensorFlow / Keras     |
| Programming Lang | Python                 |
| Federated Sim    | Manual (offline)       |
| Backend          | Flask                  |
| Frontend         | HTML, CSS, JS, Bootstrap |
| Image Processing | OpenCV, Numpy, Matplotlib |

---

## 🔄 How Federated Learning Works

This is a **simulated** Federated Learning setup:

1. Local MRI image data resides on simulated clients.
2. Each client trains the model independently on its local data.
3. Only **model weights** are sent to a central server.
4. The server **aggregates weights manually** to form a global model.
5. The final model (`trained_global_model.h5`) is used in the web app for inference only.

✅ **Data never leaves the local machine** during training — ensuring privacy.

---

## 🧬 Dataset Details

- **Source**: Brain MRI Images Dataset (open dataset)
- **Classes**: 
  - `yes/` — Tumor Present  
  - `no/` — Tumor Absent
- **Original Size**: 
  - Yes: 155 images  
  - No: 98 images
- **After Augmentation**: ~600+ images
- **Train/Test Split**: 80% Train, 20% Test

---

## 🤖 Model Details

- **Architecture**: Convolutional Neural Network (CNN)
- **Loss Function**: Binary Crossentropy
- **Optimizer**: Adam
- **Evaluation**: Achieved over **95% accuracy** on validation data
- **Output**: Binary classification (tumor/no tumor) + confidence score

---

## 📊 Severity Prediction Logic

When a tumor is detected:
- The **model’s prediction confidence** is converted into a **severity percentage**.
- Based on this value, a **medical description** is generated.

### 🎯 Example Output:

Tumor Detected
🧪 Tumor Severity: 87%
⚠️ This indicates a high-severity tumor and immediate medical attention is advised.


---

## 🖥️ Frontend & Backend

### 🔧 Backend:
- Flask server (`web_app.py`)
- Handles file uploads, model loading, and predictions

### 🎨 Frontend:
- HTML + CSS + Bootstrap
- Displays results: MRI image, tumor presence, severity, and advisory

---

## 📈 Project Flowchart

graph TD
A[Start] --> B[Load Local Data on Clients]
B --> C[Train Local Models]
C --> D[Send Weights to Server]
D --> E[Aggregate Model Weights]
E --> F[Save Global Model]
F --> G[Deploy via Flask Web App]

## 🚀 How to Run the Project

1. Clone the repository
      git clone https://github.com/your-username/your-repo-name.git

2. Navigate to project directory
      cd your-repo-name/WebApp

3. Install dependencies
      pip install -r requirements.txt

4. Run the Flask app
      python web_app.py

5. Visit in browser
      http://127.0.0.1:5000/

## ✅ Conclusion
This project demonstrates a privacy-first approach to medical image classification using Federated Learning.

🔑 Key Takeaways:
✔️ Accurate CNN-based tumor classification

✔️ Severity scoring with medical interpretation

✔️ User-friendly web interface with instant predictions

✔️ Privacy-preserving training simulation via federated approach

⚠️ This tool is for research and educational purposes. Clinical decisions should always involve a medical professional.

