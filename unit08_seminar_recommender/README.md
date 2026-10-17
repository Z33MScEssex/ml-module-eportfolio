# Unit 8 seminar: recommender system (Task 3)

**Learning outcomes:** LO1 (explainability, popularity bias), LO3

**Notebook:** [recommender_system.ipynb](recommender_system.ipynb). It uses the module's matrix factorisation
notebook (Theobald) on MovieLens 100K (Harper and Konstan, 2015), plus my answers to the SHAP follow-up
questions. The notebook downloads the data itself; the dataset licence doesn't allow it to be redistributed.

**What I found**
- **The module's own SHAP example explains a user the model knows nothing about.** User 90 has no training
  ratings, so their latent vector is still exactly its random starting value. Nearly half of their
  "explanation" is explaining noise.
- **For a user it did learn (608 ratings):** Star Wars predicted 5.26, and they gave it 5. Bio-Dome
  predicted 0.30. The item bias makes sense: it tracks real average ratings at r = 0.74. But up to 80% of
  each explanation sits in features called `latent_inter_6` and the like, which nobody can interpret.
- The full model beats a two-line bias baseline by 0.005 stars on test, and it overfits after epoch 5.
- It leans on popular films: the median recommended film has 148 ratings against 23 for a typical film.

Tasks 1 and 2 (the Yu, 2024 comparison and explainability) are written answers, covered in my reflection.
