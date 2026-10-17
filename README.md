# Machine Learning e-Portfolio

**University of Essex Online · Machine Learning (ML_PCOM7E), July 2026 · Zee Mehmood**

This repository is my e-portfolio for the Machine Learning module. Every unit has its own folder with a short
README saying what the task was, what I did, and what I found. Notebooks are saved with their outputs, so they
can be read on GitHub without running anything.

My reflective piece (1,000 words) is submitted separately, as the module asks.

## Learning outcomes

- **LO1** Articulate the legal, social, ethical and professional issues faced by machine learning professionals.
- **LO2** Understand the applicability and challenges associated with different datasets for machine learning.
- **LO3** Apply and critically appraise machine learning techniques on real-world problems, especially where
  there is technical risk and uncertainty.
- **LO4** Develop the skills to be an effective member of a development team in a virtual professional
  environment.

Where each one is evidenced: [professional development](professional_development/README.md#learning-outcomes-where-the-evidence-is).

## Artefacts by unit

| Unit | Artefact | Type | LOs |
|---|---|---|---|
| 1 to 3 | [Collaborative Discussion 1](unit01-03_collaborative_discussion_1/README.md) | Forum posts | 1, 2, 4 |
| 2 | [EDA on Auto-mpg](unit02_seminar_eda/README.md) | Seminar prep, notebook | 2, 3 |
| 3 | [Correlation and regression](unit03_correlation_regression/README.md) | e-Portfolio activity, 4 notebooks | 2, 3 |
| 4 | [Linear regression: fuel demo and population vs GDP](unit04_seminar_regression/README.md) | Seminar prep, 2 notebooks | 2, 3, 4 |
| 5 | [Jaccard coefficient calculations](unit05_jaccard/README.md) | e-Portfolio activity, notebook | 1, 2 |
| 6 | [K-Means on iris, wine and weather](unit06_seminar_kmeans/README.md) | Seminar prep, notebook | 2, 3 |
| 6 | [**Team project: Airbnb pricing**](unit06_team_project/README.md) | Summative, team | 1 to 4 |
| 7 | [Perceptron activities](unit07_perceptron/README.md) | e-Portfolio activity, 3 notebooks | 2, 3 |
| 8 | [Gradient descent and the cost function](unit08_gradient_descent/README.md) | e-Portfolio activity, notebook | 2, 3 |
| 8 | [Recommender system and SHAP](unit08_seminar_recommender/README.md) | Seminar prep, notebook | 1, 3 |
| 8 to 10 | [Collaborative Discussion 2](unit08-10_collaborative_discussion_2/README.md) | Forum posts | 1, 3, 4 |
| 9 | [CNN object recognition](unit09_cnn/README.md) | e-Portfolio activity, notebook | 1, 2, 3 |
| 10 | [CNN layers and new images](unit10_seminar_cnn/README.md) | Seminar prep, notebook | 2, 3 |
| 11 | [Model performance measurement](unit11_model_performance/README.md) | e-Portfolio activity, notebook | 1, 3 |
| 11 | [**Individual project: Bliss word classes**](unit11_individual_project/README.md) | Summative, individual | 1 to 3 |
| 11 | [Evaluation: final project vs team project](unit11_individual_project/evaluation_vs_unit06.md) | Evaluation | 3, 4 |
| All | [Professional development: skills matrix and action plan](professional_development/README.md) | PDP | 4 |

## A thread running through the portfolio: checking the numbers

The most useful habit I built on this module was not trusting a result just because the code ran. Several of
the module's own notebooks had problems that changed or hid their results. I fixed each one, marked the fix in
the notebook, and explained it.

| Where | What was wrong | Effect |
|---|---|---|
| Unit 3, linear regression | `stat` used where `stats` was imported | Notebook crashed |
| Unit 3, multiple regression | `cars.csv` not supplied | Couldn't run; sourced the original file and confirmed it matches |
| Unit 4, fuel demo | Predicted from the answer column; R² arguments reversed | Published output showed R² −18.82; fixed, 0.79 |
| Unit 6, K-Means demo | Data loaded from the author's own drive; scaled data never used | Couldn't run; the unscaled habit costs 0.53 of agreement on wine |
| Unit 7, multi-layer perceptron | Variable name only worked because of leftover memory; unseeded | Crashed in a fresh session |
| Unit 8, recommender | SHAP example explains a user with no training data | Half the "explanation" is random noise |
| Unit 9, CNN | `predict_classes` removed in TensorFlow 2.6 | Last cell crashed |
| Unit 11, performance | AUC scored on training data; "RMSE" heading shows MSE | Flattering score; mislabelled metric |

The same instinct produced my biggest contribution to the team project: [Bug Report #25](unit06_team_project/README.md#my-role-and-contributions),
which found our model was being scored on its own training data, and that our business question had no answer
in the data.

## Running the notebooks

Python 3.10 with numpy, pandas, scipy, scikit-learn, matplotlib, seaborn, missingno, shap and TensorFlow/Keras.
Each notebook runs from its own folder. The MovieLens and CIFAR-10 datasets are downloaded by the notebooks
themselves; their licences don't allow them to be redistributed here.

## References

Aeberhard, S. and Forina, M. (1992) *Wine* [Dataset]. UCI Machine Learning Repository. Available at: https://doi.org/10.24432/C5PC7J

Fisher, R.A. (1936) *Iris* [Dataset]. UCI Machine Learning Repository. Available at: https://doi.org/10.24432/C56C76

Harper, F.M. and Konstan, J.A. (2015) 'The MovieLens datasets: history and context', *ACM Transactions on Interactive Intelligent Systems*, 5(4), article 19.

Hubert, L. and Arabie, P. (1985) 'Comparing partitions', *Journal of Classification*, 2(1), pp. 193-218.

Koren, Y., Bell, R. and Volinsky, C. (2009) 'Matrix factorization techniques for recommender systems', *Computer*, 42(8), pp. 30-37.

Krizhevsky, A. (2009) *Learning multiple layers of features from tiny images*. Technical report. University of Toronto.

Lundberg, S.M. and Lee, S.-I. (2017) 'A unified approach to interpreting model predictions', *Advances in Neural Information Processing Systems 30*. Curran Associates.

Minsky, M. and Papert, S. (1969) *Perceptrons: an introduction to computational geometry*. Cambridge, MA: MIT Press.

Quinlan, R. (1993) *Auto MPG* [Dataset]. UCI Machine Learning Repository. Available at: https://doi.org/10.24432/C5859H

Rousseeuw, P.J. (1987) 'Silhouettes: a graphical aid to the interpretation and validation of cluster analysis', *Journal of Computational and Applied Mathematics*, 20, pp. 53-65.

W3Schools (no date) *Python machine learning: multiple regression*. Available at: https://www.w3schools.com/python/python_ml_multiple_regression.asp (Accessed: 12 October 2026).

World Bank (2021) *World Development Indicators: population, total and GDP (current US$)*. Washington, DC: World Bank. Supplied by the module.

Young, J. (2020) *Rain in Australia* [Dataset]. Kaggle. Available at: https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package (Accessed: 12 October 2026).

**Module materials.** The supplied notebooks are by their original authors as credited inside each one, including
Dr Mike Lakoju (Unit 7 perceptron notebooks) and Theobald (Unit 8 recommender), and were provided through the
University of Essex Online module ML_PCOM7E.

