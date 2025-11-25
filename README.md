# Neural Infix to Postfix Translator

A Deep Learning project that implements a Sequence-to-Sequence (Seq2Seq) neural network to translate mathematical formulae from traditional **Infix notation** (e.g., `a + b`) to **Postfix notation** (Reverse Polish Notation, e.g., `a b +`).

## 📌 Project Overview
Infix notation is ambiguous without parentheses (e.g., `a + b * c`), whereas Postfix notation eliminates ambiguity and is ideal for stack-based evaluation. This project uses a data-driven approach to learn these disambiguations.

* **Input:** Randomly generated Infix expressions (max depth 3).
* **Output:** Equivalent Postfix expressions.
* **Performance:** Achieved ~99% validation accuracy and ~0.065 validation loss.

## 🧠 Architecture
The model utilizes an **Encoder-Decoder** architecture built with **TensorFlow/Keras**:

* **Encoder:** 2-layer LSTM with Embedding and Dropout.
* **Decoder:** 2-layer LSTM with Embedding, Dropout, and a Dense Softmax output.
* **Inference:** Custom Greedy Autoregressive Decoding (without Beam Search).
* **Parameter Count:** ~1.8 Million parameters.

## 🛠️ Tech Stack
* Python
* TensorFlow / Keras
* NumPy

## 📊 Results
The model was trained for 30 epochs with Early Stopping and Learning Rate Reduction.

| Metric | Score |
| :--- | :--- |
| **Training Accuracy** | 99.36% |
| **Validation Accuracy** | 99.44% |
| **Prefix Accuracy Score** | ~0.97 |

## 🚀 Usage

1. **Generate Data:** The project includes a custom expression generator.
2. **Train:** Run the notebook to train the LSTM model.
3. **Inference:**
   ```python
   # Example output from model
   Infix:    ((b + d) / a)
   Expected: b d + a /
   Predicted: b d + a /
   Match:    ✅
