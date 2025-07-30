# Encoder-Decoder LSTM Network — Sequence-to-Sequence Model

This project implements an **Encoder-Decoder architecture** using **LSTM layers** in TensorFlow/Keras. It is designed for sequence-to-sequence learning tasks like **text generation**, **language translation**, or **summarization**.

> This project was created as part of a technical task for an interview.

---

## 📁 Files in This Repository

| File/Folder                  | Description |
|-----------------------------|-------------|
| `Encoder_Decoder_Network.ipynb` | The main Jupyter notebook containing model building, training, and evaluation code |
| `model.h5`                  | Trained model file including weights and architecture |
| `requirements.txt`         | List of required Python packages to run this project |
| `README.md`                | This file – explains everything about the project |
| `data/` *(optional)*       | Directory for input sample data, if any |

---

## 🧠 Model Architecture Overview

The Encoder-Decoder model follows this basic structure:

- **Encoder**: Takes an input sequence and encodes it into a fixed-size context vector using LSTM.
- **Decoder**: Receives the context vector and generates the output sequence token by token using another LSTM.

```text
Input Text → [Encoder LSTM] → Context Vector → [Decoder LSTM] → Output Text
