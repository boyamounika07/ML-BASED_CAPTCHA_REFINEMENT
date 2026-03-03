# 🔐 ML Model-Based Solution to Refine CAPTCHA

## 📌 Overview

This project presents a Machine Learning-based approach to enhance CAPTCHA systems by improving both **security** and **robustness** against automated solvers. 

A multi-output Convolutional Neural Network (CNN) is trained to recognize CAPTCHA text, and adversarial techniques (FGSM) are integrated to evaluate and strengthen CAPTCHA resistance against ML-based attacks.

---

## 🎯 Objectives

- Generate synthetic CAPTCHA datasets
- Train a CNN model to recognize CAPTCHA text
- Evaluate model performance (accuracy & confidence)
- Apply adversarial perturbations to test robustness
- Deploy an interactive web-based CAPTCHA system using Streamlit

---

## 🧠 Model Architecture

- Multi-output CNN
- 3 Convolution layers (32 → 64 → 128 filters)
- ReLU activation
- MaxPooling layers
- Dense layer (512 units)
- Separate Softmax output for each character
- Adam optimizer
- Categorical Crossentropy loss

Each character position is treated as an independent multi-class classification problem.

---

## 🛡 Adversarial Security Enhancement

This project integrates **Fast Gradient Sign Method (FGSM)** to generate adversarial CAPTCHA images.

### What it does:
- Adds small, carefully calculated perturbations to CAPTCHA images
- Perturbations are invisible to humans
- Makes automated ML solvers less reliable
- Tests model robustness under attack conditions

When enabled:
```
Original Image → FGSM Perturbation → Modified Image → CNN Prediction
```

This demonstrates AI security and adversarial robustness in CAPTCHA systems.

---

## 📂 Project Structure

```
captcha_project/

├── captcha_dataset/          # Generated CAPTCHA images  
├── adversarial.py            # FGSM adversarial example generator  
├── app.py                    # Streamlit application  
├── data_preparation.py       # Data loading & encoding  
├── generate_dataset.py       # CAPTCHA dataset generator  
├── train_model.py            # CNN model training script  
├── requirements.txt          # Dependencies  
└── README.md                 # Project documentation  
```

---

## ⚙ Installation

### 1️⃣ Clone Repository
```bash
git clone https://github.com/LokamHarika/ML_ENHANCED_CAPTCHA_REFINEMENT.git
cd ML_ENHANCED_CAPTCHA_REFINEMENT
```

### 2️⃣ Create Virtual Environment
```bash
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
```

### 3️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

---

## 🚀 Usage

### Step 1: Generate CAPTCHA Dataset
```bash
python generate_dataset.py
```

### Step 2: Train CNN Model
```bash
python train_model.py
```

Model will be saved as:
```
captcha_solver_model.h5
```

### Step 3: Run Streamlit App
```bash
streamlit run app.py
```

---

## 🌐 Streamlit Application Features

- CAPTCHA generation
- User input validation
- Model prediction display
- Character-wise accuracy
- Confidence score
- Debug mode (for analysis)
- Adversarial attack toggle
- CAPTCHA difficulty adjustment

---

## 📊 Evaluation Metrics

- Character Accuracy
- Validation Accuracy
- Validation Loss
- Confidence Score (Average Softmax Probability)


## 🧪 Technologies Used

- Python
- TensorFlow / Keras
- Streamlit
- NumPy
- Captcha Library

---

## 📌 Key Contributions

- Multi-output CNN-based CAPTCHA solver
- Integration of adversarial attack mechanism
- Interactive deployment using Streamlit
- Robustness testing framework for CAPTCHA security

---

## 📖 Acknowledgements

- Captcha – Python CAPTCHA image generator
- TensorFlow / Keras – Deep learning framework
- Streamlit – Web app framework

---
