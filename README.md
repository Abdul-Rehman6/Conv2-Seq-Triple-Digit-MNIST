# Encoder‑Decoder CNN‑LSTM Network for MNIST Triplet Classification

This repository contains an **Encoder‑Decoder** model implemented in **PyTorch**, combining a **CNN encoder** and an **LSTM decoder**, trained on a **triplet version of the MNIST dataset**.  
Instead of simple digit classification, the model processes sets of three MNIST images at once (triplets) to learn richer sequence relationships. This was developed as part of a technical interview task.

> **Note:** You can run the entire pipeline—from data loading to plotting—directly in the provided Jupyter Notebook.

---

## 📁 Repository Structure

- **Encoder_Decoder_Network.ipynb** — Main notebook with data loading, model creation, training, and evaluation.
- **best_model.pth** — Trained model weights saved in PyTorch format.
- **requirements.txt** — Python packages required to run the project.
- **README.md** — This file describing the project.

---

## 🧠 Model Architecture Overview

The Encoder‑Decoder model follows this basic structure:

- **Encoder**: A multi‑layer CNN that processes each MNIST digit image, extracts spatial features, and projects them into a fixed‑size embedding vector.
- **Decoder**: A 2‑layer LSTM that takes the sequence of three encoded embeddings and generates a sequence of digit class predictions.

Overall structure:

**Triplet Batch → [ CNN Encoder ] → Embedding Vectors → [ LSTM Decoder ] → Digit Predictions**

---

## 🛠️ Detailed Model Components

### **Encoder**

- Two convolutional layers with ReLU activation and dropout for regularization.
- Max pooling after each conv layer to reduce spatial dimensions.
- Final output is flattened and passed through a fully connected layer to produce a feature vector for each image.

### **Decoder**

- Two-layer LSTM that takes the sequence of three feature vectors from the encoder.
- Each LSTM output is passed through a linear layer to produce a classification over the 10 digit classes (0–9).
- The decoder produces three predictions per triplet, one for each image in the sequence.

---

## 🗂️ Data Loading & Preprocessing

- The project uses the **MNIST dataset** from `torchvision.datasets`.
- Data is structured as **triplets**, i.e., each sample contains three consecutive MNIST images and their corresponding labels.
- Images are converted to tensors and optionally normalized.
- A custom PyTorch Dataset is used to bundle every three images as one training sample.

---

## 🚦 Training Pipeline

- The model is trained using the **Adam optimizer** with **cross-entropy loss**.
- Training runs for a fixed number of epochs, and the best model is saved based on validation loss.
- **Early stopping** is implemented to prevent overfitting if the model stops improving.
- Training and validation accuracy are tracked and plotted over time.

---

## 📈 Evaluation & Usage

- After training, the best model is loaded and evaluated on the test set.
- The model predicts the labels for each of the three images in a triplet.
- Accuracy is computed by comparing the predicted labels with the ground truth.
- Visualizations can also be created to see sample predictions from the test set.

---

## 📦 Requirements

This project depends on the following Python packages:

- **PyTorch**
- **TorchVision**
- **Matplotlib**
- **TQDM**

All dependencies are listed in `requirements.txt` and can be installed using pip.

---
