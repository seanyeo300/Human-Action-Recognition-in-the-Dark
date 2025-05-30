# Human Action Recognition in the Dark

This repository contains my submission for the EE6222 AY2023/2024 assignment titled **"Human Action Recognition in the Dark: A Simple Exploration with Late Fusion and Image Enhancement"**. The project explores the challenge of recognising human actions from videos recorded in dark environments using traditional classification pipelines and image enhancement techniques.

## 📘 Background

Human Action Recognition (HAR) is a core task in video analysis with applications ranging from surveillance to smart homes. However, most state-of-the-art HAR models are trained on well-lit, clean datasets and perform poorly under challenging conditions such as low illumination. This project aims to:

- Investigate the impact of darkness on HAR performance.
- Explore a baseline late fusion pipeline for classification.
- Assess the benefits of applying image enhancement techniques.
- Optionally, extend the work to an end-to-end HAR model.

## 🧪 Project Description

Given a dataset containing videos across six action classes — `jump`, `run`, `sit`, `stand`, `turn`, `walk` — the objective is to:

1. Sample frames from each video.
2. Extract features using pre-trained models.
3. Train a classifier using late fusion.
4. Evaluate model performance on a test set.
5. Analyse the effect of image enhancement on classification accuracy.
6. (Optional) Design and evaluate an end-to-end HAR pipeline.

---

## 🧭 Methodology

### 1️⃣ Frame Sampling

Implemented both:
- **Uniform Sampling**: Equal intervals across the video duration.
- **Random Sampling**: Randomly select fixed number of frames.

### 2️⃣ Feature Extraction

- Pre-trained inflated 3D convolutional neural network (i3DCNNs) by Carreira & Zisserman et al. were used.
- Frame-level features are normalised using:
  - `mean = [0.07, 0.07, 0.07]`
  - `std = [0.1, 0.09, 0.08]`
- Features from all frames are pooled (average) to form a video-level descriptor.

### 3️⃣ Classification

- Evaluated traditional classifiers: SVM, Naive Bayes, MAP.
- Performance was measured using accuracy and confusion matrix on validation set.

### 4️⃣ Image Enhancement

- Applied histogram equalisation and gamma correction.
- Normalisation aligned with standard video frames:
  - `mean = [0.485, 0.456, 0.406]`
  - `std = [0.229, 0.224, 0.225]`
- Quantified impact on classification performance with and without enhancement.

### 5️⃣ End-to-End Model

- Implemented a lightweight 3D CNN for direct video classification.
- Implemented an evaluation pipeline for determining the best combination of SVM kernel and image enhancement technique

---

## 📊 Results

| Method                | Accuracy (%) |
|----------------------|--------------|
| Late Fusion + SVM    | XX.XX        |
| Late Fusion + MAP    | XX.XX        |
| With Enhancement     | ↑/↓ XX.XX    |
| End-to-End 3D CNN    | XX.XX        |

Sample outputs and visual results are available in the `results/` directory.

---

## 🔧 Tools and Libraries

- Python 3.x
- OpenCV
- NumPy, SciPy
- Scikit-learn
- PyTorch / TensorFlow (for CNNs)
- Matplotlib

---

## 📝 Report

A detailed write-up, following the ICLR format, is available in the `report/` folder as `YourFullName_YourMatriculationNo.pdf`.

---

