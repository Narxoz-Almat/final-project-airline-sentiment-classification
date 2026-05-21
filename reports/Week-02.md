# Weekly Progress Report - Week 2

## What was completed this week
- Implemented text cleaning by mapping raw textual inputs into standardized binary structures (positive: 1, negative: 0).
- Partitioned dataset into strict Train (70%), Validation (15%), and Test (15%) splits using stratified sampling.
- Built and adapted the `tf.keras.layers.TextVectorization` layer using a maximum vocabulary cap of 10,000 words.
- Constructed and fully trained the Baseline Multi-Layer Perceptron (MLP) model with `GlobalAveragePooling1D`.

## Important commits / Files changed
- `feat: implement data preprocessing and stratified splitting pipeline`
- `feat: build and execute baseline MLP text classification network`

## Experiments & Results so far
- The Baseline MLP reached a solid performance plateau on the validation split quickly, achieving an accuracy of approximately 90.7% within 5 epochs.

## Problems or Blockers
- Noticed early indications of training variance where the model began memorizing training dictionary distributions. Resolved this by introducing a strict `EarlyStopping` callback tracking `val_loss`.

## Plan for next week
- Expand the model architectures by developing Improvement 1 (Vanilla SimpleRNN) and Improvement 2 (Advanced LSTM Network) to satisfy the comparative matrix criteria.
