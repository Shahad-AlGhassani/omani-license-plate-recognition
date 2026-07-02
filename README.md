# Omani License Plate Recognition using ResNet50 CRNN

## Overview

This project implements a Deep Learning based Optical Character Recognition (OCR) system for recognizing alphanumeric sequences from Omani license plate images.

The model uses a CNN-RNN architecture combining a pretrained ResNet50 convolutional neural network with a Bidirectional LSTM network for sequence prediction.

The model is trained using Connectionist Temporal Classification (CTC) Loss, which allows the network to predict character sequences without requiring character-level alignment.

---

## Model Architecture

The proposed architecture consists of:

### CNN Feature Extractor
- ResNet50 pretrained on ImageNet
- Extracts visual features from license plate images

### Sequence Modeler
- Two-layer Bidirectional LSTM
- Learns character order and dependencies

### Classification Layer
- Fully connected layer
- Outputs character probabilities

### CTC Decoder
- Converts predictions into the final license plate text

Architecture flow:

```
Input Image
     |
     v
ResNet50 CNN Backbone
     |
     v
Feature Extraction
     |
     v
Bidirectional LSTM
     |
     v
Fully Connected Layer
     |
     v
CTC Decoding
     |
     v
Recognized License Plate
```

---

## Technologies Used

- Python
- PyTorch
- Torchvision
- Pandas
- NumPy
- Pillow
- Jiwer

---

## Repository Structure

```
resnet50-crnn-license-plate-ocr/

├── ResNet50_CRNN_License_Plate_Recognition.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Project Notebook

The notebook includes:

- Importing required libraries
- Dataset loading and preprocessing
- Character vocabulary generation
- Custom PyTorch Dataset implementation
- DataLoader preparation
- ResNet50 CRNN model implementation
- CTC Loss configuration
- Training process
- Validation evaluation
- Prediction generation

---

## Dataset

The dataset contains Omani license plate images with their corresponding text labels.

The dataset is not included in this repository due to size limitations.

The notebook loads the dataset from Google Drive.

Expected dataset format:

```
image_path,label
```

Example:

```
train/10188R.jpg,10188R
```

---

## Training Details

The model is trained using:

- Model: ResNet50 CRNN
- Optimizer: Adam
- Loss Function: CTC Loss
- Learning Rate Scheduler: ReduceLROnPlateau
- Epochs: 50

The best model is selected based on the lowest validation Character Error Rate (CER).

---

## Evaluation Metrics

The model performance is evaluated using:

### Exact Match Accuracy

Measures the percentage of license plates that are predicted completely correctly.

### Character Error Rate (CER)

Measures the difference between the predicted sequence and the actual license plate text.

Lower CER indicates better performance.

---

## Installation

Install the required dependencies:

```bash
pip install -r requirements.txt
```

---

## Running the Project

The project can be executed using:

- Google Colab
- Jupyter Notebook

Open the notebook:

```
ResNet50_CRNN_License_Plate_Recognition.ipynb
```

and run the cells sequentially.

---

## Purpose

This project was developed as part of a university Deep Learning course project.

---

## License

This project is for educational purposes only.
