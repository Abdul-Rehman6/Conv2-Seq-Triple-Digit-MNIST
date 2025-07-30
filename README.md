# Encoder‑Decoder CNN‑LSTM Network for MNIST Triplet Classification

This repository contains an **Encoder‑Decoder** model implemented in **PyTorch**, combining a **CNN encoder** and an **LSTM decoder**, trained on a **triplet version of the MNIST dataset**.  
Instead of simple digit classification, the model processes sets of three MNIST images at once (triplets) to learn richer sequence relationships. This was developed as part of a technical interview task.

---

## 📁 Repository Structure

```text
encoder-decoder-triplet-mnist/
│
├── Encoder_Decoder_Network.ipynb   ← Jupyter Notebook: data loading, model definition, training loop, evaluation, plots
├── best_model.pth                  ← Saved best‑validation‑loss model weights (PyTorch state_dict)
├── requirements.txt                ← Python dependencies
├── .gitignore                      ← Untracked files (cache, checkpoints, env, etc.)
├── README.md                       ← This file

---

## 🧠 Model Architecture Overview

The Encoder-Decoder model follows this basic structure:

- **Encoder**: Takes an input sequence and encodes it into a fixed-size context vector using LSTM.
- **Decoder**: Receives the context vector and generates the output sequence token by token using another LSTM.

```text
Input Text → [Encoder LSTM] → Context Vector → [Decoder LSTM] → Output Text
