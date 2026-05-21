# Weekly Progress Report - Week 4

## What was completed this week
- Evaluated all three trained networks (Baseline MLP, SimpleRNN, LSTM) against the isolated test partition.
- Gathered evaluation metrics: Accuracy, Precision, Recall, and F1-Score.
- Generated and saved structural evaluation plots (`confusion_matrices_comparison.png` and learning curves).
- Conducted an automated Error Analysis to inspect specific failure scenarios.
- Compiled and pushed the comprehensive `final-report.md`.

## Important commits / Files changed
- `plots: save final model learning curves and comparative confusion matrices`
- `docs: add final-report.md outlining results, limitations, and error diagnostics`
- `dump: serialize best performing network weights into models directory`

## Experiments & Results so far
- Final test metrics proved that the **LSTM Network** achieved the most balanced generalized representation (F1-Score: ~0.8265), outperforming the SimpleRNN and matching the speed efficiency of the Baseline MLP while showing better resilience.
- Automatically saved the optimized state weights as `best_nlp_model.keras`.

## Problems or Blockers
- None. The full pipeline runs automatically end-to-end without errors or missing variable dependencies.

## Plan for next week
- Deliver oral presentation defense and complete the deep learning theoretical written examination.
