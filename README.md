# Glaucoma Detection Using Quality-Aware CNN and EfficientNet-B0

## 📌 Project Overview

This project develops and evaluates deep learning models for automated glaucoma detection from retinal fundus images using the **Hillel Yaffe Glaucoma Dataset (HYGD)**. Three different pipelines were investigated:

1. **Baseline Custom CNN**
2. **Quality-Aware Custom CNN**
3. **EfficientNet-B0 (Transfer Learning)**

To ensure reliable evaluation and eliminate data leakage, all experiments were conducted using a **strict Patient-Level Split**, where images from the same patient never appear across training, validation, and testing subsets.

The primary objective is to maximize diagnostic performance while minimizing clinically dangerous **False Negatives (FN)**, where glaucoma cases are incorrectly classified as healthy.

---

## 👥 Group Members

| No. | Name                        | Student ID      |
| --- | --------------------------- | --------------- |
| 1   | **Maria Teresa Cundrik W.** | 235091000111024 |
| 2   | **Dita Safira Arini**       | 235091001111019 |
| 3   | **Nur Nilam Sari**          | 235091001111031 |
| 4   | **Chicha Meylina Nuraini**  | 235091001111022 |

### Institution

**Bachelor of Actuarial Science**
 Faculty of Sciences, Technology, and Mathematics 
**Universitas Brawijaya**
Malang, Indonesia

---

## 🏥 Clinical Motivation

Glaucoma is one of the leading causes of irreversible blindness worldwide. Early detection is essential because vision loss caused by glaucoma cannot be restored.

In medical screening systems:

* **False Negatives (FN)** are highly dangerous because affected patients may remain untreated.
* **False Positives (FP)** increase unnecessary referrals but are generally less harmful than missed diagnoses.

Therefore, model evaluation focuses not only on accuracy but also on sensitivity, ROC-AUC, and overall diagnostic reliability.

---

## 📂 Dataset

This project utilizes the **Hillel Yaffe Glaucoma Dataset (HYGD)**.

**Dataset Source:**

https://physionet.org/content/hygd/1.0.0/

### Dataset Citation

Abramovich, O., Pizem, H., Fhima, J., Berkowitz, E., Gofrit, B., Van Eijgen, J., Blumenthal, E., & Behar, J. (2025).

*Hillel Yaffe Glaucoma Dataset (HYGD): A Gold-Standard Annotated Fundus Dataset for Glaucoma Detection (Version 1.0.0).* PhysioNet.

DOI: https://doi.org/10.13026/z0ak-km33

---

## 🧠 Model Architectures

### 1. Baseline Custom CNN

A lightweight convolutional neural network designed specifically for glaucoma classification from retinal fundus images.

### 2. Quality-Aware Custom CNN

An enhanced version of the baseline architecture that incorporates image-quality information during learning. The objective is to improve the model's confidence and discrimination capability across varying image conditions.

### 3. EfficientNet-B0 (Fine-Tuned)

A transfer learning approach based on the EfficientNet-B0 architecture pre-trained on ImageNet and subsequently fine-tuned on HYGD.

---

## ⚙️ Experimental Setup

### Data Splitting

* Patient-Level Split
* Independent Test Set
* No Patient Overlap
* Data Leakage Prevention

### Evaluation Metrics

* Accuracy
* Precision
* Sensitivity (Recall)
* Specificity
* F1-Score
* ROC-AUC
* Confusion Matrix Analysis

Classification thresholds were optimized to address class imbalance between:

* **GON+ (Glaucoma)**
* **GON− (Healthy)**

---

# 📊 Final Performance Comparison

| Metric               | Baseline CNN | Quality-Aware CNN | EfficientNet-B0 |
| -------------------- | ------------ | ----------------- | --------------- |
| Accuracy             | 89.80%       | 89.80%            | **92.86%**      |
| Precision            | **100.00%**  | **100.00%**       | 97.22%          |
| Sensitivity (Recall) | 86.67%       | 86.67%            | **93.33%**      |
| Specificity          | **100.00%**  | **100.00%**       | 91.30%          |
| F1-Score             | 0.9286       | 0.9286            | **0.9524**      |
| ROC-AUC              | 0.9478       | 0.9606            | **0.9849**      |

---

## 📈 Confusion Matrices

### Baseline Custom CNN

TP = 65 | TN = 23
FP = 0 | FN = 10

### Quality-Aware Custom CNN

TP = 65 | TN = 23
FP = 0 | FN = 10

### EfficientNet-B0

TP = 70 | TN = 21
FP = 2 | FN = 5

---

## 📈 Performance Improvement Over Baseline CNN

### Quality-Aware Custom CNN

* **Δ ROC-AUC:** +0.0128

### EfficientNet-B0

* **Δ Accuracy:** +0.0306
* **Δ Precision:** -0.0278
* **Δ Sensitivity (Recall):** +0.0666
* **Δ Specificity:** -0.0870
* **Δ F1-Score:** +0.0238
* **Δ ROC-AUC:** +0.0371

---

# 🔍 Key Findings

### 1. Reduction of False Negatives

EfficientNet-B0 reduced missed glaucoma cases from **10** to **5**, representing a **50% reduction in False Negatives**, which is highly valuable in clinical screening applications.

### 2. Effectiveness of Quality-Aware Learning

The Quality-Aware CNN improved ROC-AUC from **0.9478** to **0.9606**, demonstrating enhanced discriminative ability through image-quality-aware learning.

### 3. Lightweight Models vs Transfer Learning

EfficientNet-B0 achieved the strongest overall classification performance, including:

* Highest Accuracy
* Highest Recall
* Highest F1-Score
* Highest ROC-AUC

Meanwhile, the Quality-Aware CNN maintained:

* 100% Precision
* 100% Specificity
* Zero False Positives

making it suitable for computationally constrained clinical environments.

---

# 🚀 Technologies Used

* Python
* TensorFlow / Keras
* NumPy
* Pandas
* OpenCV
* Scikit-Learn
* Matplotlib
* EfficientNet

---

# 📁 Repository Structure

```text
├── data/
├── notebooks/
├── models/
├── results/
├── figures/
├── README.md
└── requirements.txt
```

