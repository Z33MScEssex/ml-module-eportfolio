# Unit 3: correlation and regression

**Learning outcomes:** LO2, LO3

**Task.** Run the four supplied notebooks and change the data to see how correlation and regression respond.

| Notebook | What I changed | Headline |
|---|---|---|
| [ex1_covariance_pearson_correlation.ipynb](ex1_covariance_pearson_correlation.ipynb) | noise level, units, shape, one outlier | Covariance barely moved as noise grew; correlation fell from 1.00 to 0.23. A perfect U-shape scores r = 0.00. One outlier lifted r from 0.14 to 0.84. |
| [ex2_linear_regression.ipynb](ex2_linear_regression.ipynb) | fixed a bug, removed and added points, predicted far outside the data | The supplied code crashed (`stat` vs `stats`). One point moved the slope from −1.75 to −2.88. At x = 60 the line predicts −2. |
| [ex3_multiple_linear_regression.ipynb](ex3_multiple_linear_regression.ipynb) | checked the model on unseen cars, scaled the coefficients | It's barely better than guessing the average (5.6 g vs 5.9 g error). The notebook's own example car is heavier than any car in the data. |
| [ex4_polynomial_regression.ipynb](ex4_polynomial_regression.ipynb) | degrees 1 to 9, leave-one-out error | Training R² keeps rising, but error on unseen points is lowest at degree 3 and doubles by degree 9. That's overfitting. |

**Data note.** Exercise 3 reads `cars.csv`, which wasn't supplied. The code matches the W3Schools multiple
regression tutorial, so I used that file (W3Schools, no date). It reproduces the notebook's coefficients
exactly, which confirms it's the same data.
