# Data Layer & Pipeline Configuration

## 1. Dataset Source and Licensing
- **Dataset Name:** Twitter Airline Sentiment Dataset
- **Source:** Hosted officially on Kaggle (Crowdflower open-source collection)
- **Data Access:** Automated completely via the modern `kagglehub` API interface (`kagglehub.dataset_download("crowdflower/twitter-airline-sentiment")`).
- **Policy Compliance:** In strict adherence to the course instructions (*"Large dataset files should not be committed to GitHub"*), the raw CSV file containing the data stream is bypassed by `.gitignore` and downloaded dynamically at runtime.

## 2. Dataset Properties & Statistics
- **Total Initial Records:** 14,640 records containing customer airline tweets.
- **Task Formulation:** Sequence Text Classification (Sentiment Polarity Mapping).
- **Target Optimization:** To stabilize gradient updates and create a solid operational pipeline for Deep Learning architectures (MLP, RNN, LSTM), all neutral classes were purged. 
- **Cleaned Dataset Volume:** 11,541 rows of heavily polarized text.
  - **Negative Sentiment (Class 0):** 9,178 rows
  - **Positive Sentiment (Class 1):** 2,363 rows

## 3. Preprocessing and Vectorization Specifications
- **Input Features:** Raw text tweets containing noisy structural components (e.g., airline handles like `@USAirways`, web URLs, and colloquial abbreviations).
- **Text Standardization:** Done natively inside the `tf.keras.layers.TextVectorization` layer to lowercase tokens and strip punctuation maps automatically.
- **Vocabulary Constraint (`MAX_WORDS`):** Capped at the top 10,000 most frequent tokens to maintain a dense, compute-efficient embedding footprint.
- **Sequence Padding (`MAX_LEN`):** Constrained strictly to 50 words based on EDA sentence length frequency distributions. Longer sentences are truncated, and shorter ones are post-padded with zeros.

## 4. Evaluation Split Strategy
The cleaned token matrix was partitioned into an isolated validation and test layout using stratified sampling (`stratify=labels`) to ensure uniform class distributions across all pipes:
- **Training Partition:** 70% (8,078 reviews used for updating structural cell weights)
- **Validation Partition:** 15% (1,731 reviews used for `EarlyStopping` monitoring and hyperparameter checks)
- **Testing Partition:** 15% (1,732 reviews completely isolated for unfair bias control and error logs)
