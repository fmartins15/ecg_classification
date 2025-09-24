
---

## README (English)

```markdown
# ECG Classification with Deep Learning

[![Python](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/)  
Classification of ECG signals using **Convolutional Neural Networks (CNNs)** and **Recurrent Neural Networks (RNNs)** (LSTM/GRU), applied to the PTB-XL dataset.

---

## Overview

Cardiovascular diseases account for **31% of global deaths** (~17.9 million/year). Early detection via ECG is crucial for prevention and reducing hospital readmissions.  

This project explores **Deep Learning architectures** for **multilabel ECG classification**, including:
- CNN vs RNN benchmarking  
- Preprocessing and data augmentation  
- Hyperparameter optimization (Grid Search, Learning Rate Scheduling)  

---

## Dataset: PTB-XL

- **21,799 ECG records** (10s each, 12 leads)  
- **18,869 patients**  
- Sampling: 100 Hz  
- **Multilabel annotations**: multiple diagnoses per record  

### Diagnostic Superclasses
- **NORM** – Normal ECG  
- **MI** – Myocardial Infarction  
- **STTC** – ST/T Wave Change  
- **CD** – Conduction Disturbance  
- **HYP** – Hypertrophy  

---

## ⚙️ Methodology

### Preprocessing
- Train/validation/test split  
- Data structured as 3D arrays (patient × samples × leads)  

### Evaluated Models
- **Custom CNN**  
- **Smigiel CNN Adapted and Optimized**  
- **Smigiel CNN + Batch Normalization**  
- **RNNs: LSTM and GRU**  

### Data Augmentation
- Random cropping + Zero Padding  
- Temporal shifting  
- Gaussian noise  
- Amplitude scaling  

### Evaluation Metric
- **AUROC** (Area Under ROC Curve)  

---

## Results

- CNNs and RNNs achieved **~90% AUROC**  
- **GRU** slightly outperformed LSTM  
- Smigiel CNN + **Batch Normalization** = best generalization  
- **HYP class (Hypertrophy)** → lowest AUROC (class imbalance)  

---

## How to Run

```bash
# Clone repository
git clone https://github.com/fmartins15/ecg_classification.git
cd ecg_classification

# Create virtual environment
python -m venv venv
source venv/bin/activate   # Linux/macOS
# or venv\Scripts\activate (Windows)

# Install dependencies
pip install -r requirements.txt

# Open notebooks
jupyter notebook
