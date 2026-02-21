# Incident Catching Demo

ML system that predicts service incidents 15+ minutes before they occur, 
using sliding-window classification over multivariate CloudWatch-style metrics.

## Results
- **Incident recall**: 4/4 = 100%
- **Mean lead time**: 46.8 minutes
- **Alert rate**: 6.4 alerts/day

## Models
- **LightGBM** on 113 handcrafted features (primary, full pipeline)
- **1D-CNN** on raw sequences (comparison)

## Stack
Python, LightGBM, PyTorch, scikit-learn, pandas, numpy

## Structure
```
data/          # synthetic dataset generation
src/           # feature extraction, alerting logic
models/        # saved model weights
notebooks/     # pattern_v2_improved, sliding_window, 
               # baseline_rule, model_lgbm_cnn, alerting_evaluation
```

## Quickstart
```bash
# 1. Generate data
jupyter notebook notebooks/pattern_v2_improved.ipynb
# 2. Build windows + features
jupyter notebook notebooks/sliding_window.ipynb
# 3. Train models
jupyter notebook notebooks/model_lgbm_cnn.ipynb
# 4. Evaluate alerting system
jupyter notebook notebooks/alerting_evaluation.ipynb
```

## Report
Full write-up: [Google Doc](https://docs.google.com/document/d/1x9d5RcJeLzSX28sqEb1Bui1PgiPKZf645gJgDKNAcvY/edit?usp=sharing)
