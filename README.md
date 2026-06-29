# Alzheimers detection model
# Alzheimer's Detection Using CNN

A deep learning model for classifying Alzheimer's disease severity from MRI brain scans using a custom 3-layer Convolutional Neural Network.

## Overview

This project classifies MRI images into four categories:
- Non Demented
- Very mild Dementia
- Mild Dementia
- Moderate Dementia

**Test Accuracy: 99.98%**

## Dataset

- **Source**: OASIS Dataset
- **Size**: 86,437 MRI brain scan images
- **Split**: 80% training, 20% validation

## Model Architecture

3-Layer CNN with:
- **Conv Layer 1**: 3 → 16 channels + BatchNorm + ReLU + MaxPool
- **Conv Layer 2**: 16 → 32 channels + BatchNorm + ReLU + MaxPool
- **Conv Layer 3**: 32 → 64 channels + BatchNorm + ReLU + MaxPool
- **Fully Connected**: 256 units + Dropout(0.5) → 4 class outputs

Input size: 224×224 RGB images

## Image Preprocessing

- CLAHE (Contrast Limited Adaptive Histogram Equalization) for contrast enhancement
- Bilateral filtering for noise reduction
- Normalization with ImageNet-style statistics

## Training Details

- **Optimizer**: SGD (lr=0.001)
- **Loss Function**: CrossEntropyLoss
- **Epochs**: 8
- **Batch Size**: 8
- **Device**: CUDA GPU

## Requirements
- **pip install -r requirements.txt

## Installation

```bash
pip install torch torchvision opencv-python scikit-learn torchmetrics kagglehub
```

## Usage

1. Download the OASIS dataset via Kaggle
2. Update `DATASET_PATH` in the notebook
3. Run cells sequentially to preprocess data, train, and evaluate

## Results

| Metric | Value |
|--------|-------|
| Test Accuracy | 99.98% |
| Training Epochs | 8 |
| Total Images | 86,437 |
