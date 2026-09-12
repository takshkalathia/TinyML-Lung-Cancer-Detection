# TinyML-Assisted Energy and Space Efficient Framework for Lung Cancer Detection

A TinyML-assisted deep learning framework for binary lung cancer classification using CT scan images, lightweight neural networks, optimizer comparison, and post-training quantization for resource-constrained edge deployment.

## Overview

Lung cancer detection from CT scan images is an important medical imaging application where artificial intelligence can assist in identifying patterns associated with disease.

This project investigates an energy- and space-efficient approach for classifying lung CT scan images into **Benign** and **Malignant** categories. Multiple lightweight deep learning models and optimizers are evaluated to identify a suitable model for the application.

The best-performing model is then converted into a lightweight **TensorFlow Lite (TFLite)** model using post-training quantization, enabling potential deployment on resource-constrained edge and TinyML platforms.

> **Disclaimer:** This project is a research and educational prototype. It is not intended to replace professional medical diagnosis or clinical decision-making.

## Proposed Framework

The proposed framework consists of four major layers:

1. **Hospital Layer** – Collection of medical imaging data.
2. **Prediction Layer** – Image preprocessing, augmentation, and deep learning-based classification.
3. **TinyML Layer** – Model compression using post-training quantization.
4. **Output Layer** – Lightweight inference on resource-constrained or edge devices.

![Proposed Framework](results/Framework.png)

## Dataset

## Dataset

This project uses the **IQ-OTH/NCCD Lung Cancer Dataset**, obtained from Kaggle.

The dataset contains CT scan images categorized into three classes:
- **Benign**
- **Malignant**
- **Normal**

For this project, only the **Benign** and **Malignant** classes are used for binary lung cancer classification. The **Normal** class is excluded.

The dataset is not included in this repository. You can access it here:

**Dataset:** [IQ-OTH/NCCD - Lung Cancer Dataset](https://www.kaggle.com/datasets/adityamahimkar/iqothnccd-lung-cancer-dataset)

During model training, images are resized, normalized using the MobileNetV2 preprocessing function, and training-time data augmentation is applied.

The labels used in the project are:

- `0` → Benign
- `1` → Malignant

The images are stored in `.jpg` format.

The dataset was divided into:

- **70% Training**
- **30% Validation**

The images were resized and normalized before being provided to the deep learning models. Data augmentation was also applied during training to introduce additional variations and improve model robustness.

The complete medical imaging dataset is **not included in this repository** because it is a third-party dataset. Users should obtain the dataset from its original source and follow its applicable license and terms of use.

## Methodology

The overall workflow of the project is:

```text
CT Scan Dataset
       ↓
Benign & Malignant Selection
       ↓
Image Preprocessing
       ↓
Resizing + Normalization
       ↓
Data Augmentation
       ↓
70% Training / 30% Validation
       ↓
Model Training
       ↓
Optimizer Comparison
       ↓
Performance Evaluation
       ↓
Best Model Selection
       ↓
Post-Training Quantization
       ↓
TFLite Model
       ↓
Lightweight Edge Inference
       ↓
Benign / Malignant Prediction
