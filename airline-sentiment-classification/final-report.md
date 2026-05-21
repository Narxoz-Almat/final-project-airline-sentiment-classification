# Final Project Report: NLP Sentiment Analysis

## 1. Task Definition & Dataset Exploration
- **Problem Type:** Binary Sequence Text Classification.
- **Dataset:** Twitter Airline Sentiment Dataset (Kaggle). Cleaned by removing neutral responses to stabilize binary optimization.
- **Data Splitting:** Data was strictly partitioned into a **70% Training / 15% Validation / 15% Testing** split using stratified sampling to keep class ratios uniform.

## 2. Core Architectures
- **Baseline MLP:** Converts word tokens into dense embedding dimensions and applies spatial averaging. Fast but lacks context awareness.
- **SimpleRNN:** Learns temporal dynamics by passing hidden states sequentially, but suffers from gradient clipping issues on longer text.
- **LSTM Network:** Addresses long-term memory dependencies using explicit gate controllers (input, forget, output gates). Built-in with `dropout=0.2` and `recurrent_dropout=0.2` for regularization.

## 3. Training Paradigm
- **Loss:** `binary_crossentropy`
- **Optimizer:** Adam (Learning Rate = 0.001)
- **Overfitting Control:** Implemented Keras `EarlyStopping` monitoring `val_loss` with a patience threshold of 2 epochs.

## 4. Empirical Evaluation Summary
*Below is the performance log recorded on the isolated test partition:*

| Model | Accuracy | Precision | Recall | F1-Score |
| :--- | :---: | :---: | :---: | :---: |
| **Baseline MLP** | 0.9070 | 0.8250 | 0.7810 | 0.8024 |
| **Simple RNN** | 0.8540 | 0.7410 | 0.6930 | 0.7162 |
| **LSTM Network** | 0.9125 | 0.8415 | 0.8120 | 0.8265 |

**Core Finding:** The LSTM model demonstrated the superior F1-Score, showing that gating mechanisms provide stable semantic representation for noisy textual sentiment.

## 5. Error Analysis
By dumping misclassified examples via the test pipe, the primary failure points include:
1. **Sarcasm Detection:** Text containing heavy praise combined with negative situational context.
2. **Double Negatives:** Sentences containing convoluted complaints that shift standard semantic polarities.