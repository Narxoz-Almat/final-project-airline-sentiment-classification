# Sentiment Classification of Airline Reviews Using Deep Learning

**Course:** Deep Learning (Narxoz University)  
**Instructor:** Ardak Shalakrbayuly  
**Grade Target:** C+ Level (70 points)  

## Project Overview
This repository contains a deep learning pipeline designed to analyze customer sentiment from airline tweets. The system reads text reviews and classifies them as either **Positive** or **Negative** to automate customer satisfaction monitoring.

## Implemented Models (C+ Criteria)
To meet the evaluation matrix requirements, three distinct architectures were developed and evaluated:
1. **Baseline Model:** Multi-Layer Perceptron (MLP) using Word Embeddings and Global Average Pooling.
2. **Improvement 1:** Vanilla Recurrent Neural Network (SimpleRNN) to process sequential text constraints.
3. **Improvement 2:** Long Short-Term Memory (LSTM) Network integrated with **Dropout regularization** to counter overfitting and tackle vanishing gradients.

## Repository Setup
- `student_info.txt`: Official submission identification card.
- `sentiment_analysis.ipynb`: The main notebook optimized to run error-free on Google Colab.
- `final-report.md`: Deep analytical report including cross-model comparison tables.
- `results/`: Directory housing generated evaluation graphs, loss curves, and loss maps.