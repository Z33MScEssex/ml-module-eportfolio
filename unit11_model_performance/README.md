# Unit 11: model performance measurement

**Learning outcomes:** LO1, LO3

**Task.** Change parameters and see the effect on AUC and R²:
[model_performance_measurement.ipynb](model_performance_measurement.ipynb).

**What I found**
- **The module scores its breast cancer AUC on the training data.** On a proper split, training AUC beats
  unseen AUC at every setting, and hits a perfect 1.0000 when regularisation is switched off. This is the same
  mistake I caught in our Unit 6 team notebook.
- **AUC and accuracy can disagree.** With heavy regularisation, unseen AUC stays at 0.965 while accuracy falls to
  0.637. The ranking is fine; the yes/no cut-off isn't.
- **Accuracy lies on imbalanced data.** With 2% positives, a model that always says "no" scores 97.5% accuracy
  and catches nobody.
- **R² below zero means worse than guessing the average.** And the cell headed "RMSE" in the module actually
  shows MSE.
