# 🗣️ English to French Language Translation using Seq2Seq LSTM

This project implements a **sequence-to-sequence (Seq2Seq)** model with **LSTM networks** for translating English sentences into French using the [Language Translation English-French Dataset](https://www.kaggle.com/datasets/devicharith/language-translation-englishfrench).

---

## 📁 Dataset

- **Source**: Kaggle ([link](https://www.kaggle.com/datasets/devicharith/language-translation-englishfrench))
- **File**: `eng_-french.csv`
- Contains paired sentences in English and French.

---

## 🧹 Preprocessing Steps

1. Lowercasing all text.
2. Removing punctuation, digits, and extra spaces.
3. Adding `START_` and `_END` tokens to French sentences.
4. Filtering sentences with max length > 20 words.
5. Tokenizing and indexing words.
6. Splitting into training and test sets.

---

## 🧠 Model Architecture

- **Encoder**:
  - Embedding layer
  - LSTM layer (returns final state only)
- **Decoder**:
  - Embedding layer
  - LSTM layer (uses encoder states as initial state)
  - Dense output layer with softmax activation

---

## 📊 Training

- **Optimizer**: `RMSprop`
- **Loss**: `categorical_crossentropy`
- **Batch size**: `128`
- **Epochs**: `50`
- Custom data generator used for batch-wise data feeding

---

## 🧪 Evaluation

- Validation performed on a test set (20% split)
- Evaluation metrics: Loss and Accuracy

---

## 🛠️ Requirements

- Python 3.x
- TensorFlow / Keras
- Pandas, NumPy
- Matplotlib, Seaborn
- scikit-learn

Install all requirements:

```bash
pip install -r requirements.txt
```

---

## 🚀 Usage

1. Upload your `kaggle.json` in Colab.
2. Run the training notebook.
3. Model will start translating after training completes.

---

## 📌 Notes

- Trained using ~25,000 sentence pairs.
- The LSTM-based Seq2Seq model learns to predict French translations from English input.
- You can later extend this project to include:
  - Attention mechanism
  - Transformer models
  - BLEU score evaluation

---
