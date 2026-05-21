# Weekly Progress Report - Week 1

## What was completed this week
- Defined the project scope focusing on NLP Binary Sequence Classification.
- Selected the official "Twitter Airline Sentiment" dataset hosted on Kaggle.
- Set up the GitHub repository structure following the target C+ level complexity matrix guidelines.
- Created mandatory project tracking documentation (`student_info.txt` and `README.md`).
- Performed initial Exploratory Data Analysis (EDA) on the raw text data.

## Important commits / Files changed
- `added student_info.txt and project core directories`
- `added initial README.md with project layout setup`
- `added data exploration scripts`

## Experiments & Results so far
- Checked class distribution: identified that removing the 'neutral' reviews creates a highly stable and balanced binary classification pipeline (Positive vs. Negative).
- Analyzed sentence length frequency, setting an optimal token cutoff sequence length to 50 words to minimize execution latency.

## Problems or Blockers
- Encountered initial directory path mismatches when structuring files locally versus Google Colab environment variables, which were resolved by implementing the `pathlib` library.

## Plan for next week
- Build the data preprocessing pipeline, clean text streams, implement the Keras `TextVectorization` layer, and train the Baseline MLP model.
