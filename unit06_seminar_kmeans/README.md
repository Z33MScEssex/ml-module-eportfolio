# Unit 6 seminar: K-Means clustering

**Learning outcomes:** LO2, LO3

**Task.** Study the module's K-Means demo, then do at least one of three clustering tasks. I did all three:
[kmeans_iris_wine_weather.ipynb](kmeans_iris_wine_weather.ipynb).

The module's demo couldn't be run. It loads its data from a path on the original author's own Windows drive.
Reading it, I also found that it scales the data and then clusters the unscaled copy.

| Task | Result |
|---|---|
| A. Iris, K = 3 | Agreement with the real species (adjusted Rand index) 0.73. Setosa is separated perfectly; the other two overlap. The silhouette score would have picked K = 2, not 3. |
| B. Wine, K = 3 | 0.37 unscaled, **0.90 scaled**. Unscaled, one column (Proline) is 99.8% of the variance, so K-Means just sorts by it. |
| C. Weather, K = 2 to 6 | No natural groups (silhouette 0.16 to 0.24). But the K = 3 slices read as hot and dry, cool and settled, and wet and windy. The wet and windy cluster saw rain the next day 44% of the time, against 22% overall. |

**The lesson I'll keep:** scaling is a decision, not a reflex. It transformed wine and made iris worse.

**Data:** iris (Fisher, 1936) and wine (Aeberhard and Forina, 1992), both from the UCI Machine Learning
Repository; weatherAUS from Kaggle. All supplied by the module.
