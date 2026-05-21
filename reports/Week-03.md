# Weekly Progress Report - Week 3

## What was completed this week
- Implemented and trained a Vanilla Recurrent Neural Network (`SimpleRNN`) to capture temporal relations between tokens.
- Developed an advanced Long Short-Term Memory (`LSTM`) network utilizing specialized memory gates.
- Resolved Keras execution bugs regarding improper parameter definitions inside the recurrent cell arguments.
- Applied systematic regularization tactics including explicit hidden layer `Dropout` and `recurrent_dropout`.

## Important commits / Files changed
- `fix: resolve unrecognized cell arguments error in SimpleRNN layer configuration`
- `feat: integrate LSTM architecture with structural dropout regularization`

## Experiments & Results so far
- Evaluated sequential models: SimpleRNN showed validation limitations due to vanishing gradient attributes on longer text structures. LSTM demonstrated stable convergence patterns, leveraging its internal memory cells to safely bypass vanishing gradients.

## Problems or Blockers
- Encountered a `ValueError` regarding Keras recurrent layer parameters during the SimpleRNN execution step. Solved the problem by restructuring the layer setup configurations.

## Plan for next week
- Run final comparative evaluations across all three architectures, generate performance charts, export metrics tables, and perform a deep Error Analysis.
